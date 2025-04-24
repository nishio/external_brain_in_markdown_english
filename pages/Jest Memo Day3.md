---
title: "Jest Memo Day3"
---

from  [[Jest Memo]]
Jest Memo Day3
--- day 3
- `MissingAPIError: indexedDB API missing`
    - As with Firestore, the code that touches IndexeDB needs to be isolated and replaced by a mock.
    - Last time, I did a mock where I cut out and exported the code after taking the values from Firestore as follows, and replaced getNewTalkID with a Promise that calls this directly
ts

```typescript
// exported for test
export const _gotNewTalkID = (text: string) => {
  return localDB.talks
    .orderBy("id")
    .reverse()
    .limit(1)
    .toArray()
    .then((x) => {
      const previousTalkID = x[0]?.TalkID;
      if (previousTalkID !== undefined) {
        setGlobal({ TalkID: text, previousTalkID: x[0].TalkID });
      } else {
        setGlobal({ TalkID: text, previousTalkID: "" });
      }
      localDB.talks.add({ TalkID: text });
    });
};
```

- Split Promise into three functions: read, use, and write, while specifying the type of Promise.
    - [[Jest mocking does not affect calls within the same module]], so let's mock only the parts that touch IndexedDB by placing them in a separate module.
- User Module Mock [doc [https://jestjs.io/docs/ja/manual-mocks#%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E](https://jestjs.io/docs/ja/manual-mocks#%E3%83%A6%E3%83%BC%E3%82%B6%E3%83%BC%E3%83%A2%E3%82%B8%E3%83%A5%E3%83%BC%E) 3%83%AB%E3%81%AE%E3%83%A2%E3%83%83%E3%82%AF]
    - I see
    - But I'd like to see it implemented two ways.
__mocks__/managePreviousTalkID.ts

```typescript
// no previoud id
export const getPreviousTalkID = (): Promise<string> => {
  return Promise.resolve("");
};
export const MOCK_PREVIOUS_ID_EXISTS = (): Promise<string> => {
  return Promise.resolve("test");
};

export const updatePreviousTalkID = (currentTalkID: string): void => {};
```

- Top screen rendering test now works.
    - If I don't put just.mock at the top level instead of in the test case, it doesn't mock as expected, why?
    - I'd like to test switching the behavior of multiple mocks...
- > I have to put jest.mock at the top level instead of in the test case to get it mocked as expected, why?
    - > [docs](https://jestjs.io/docs/ja/manual-mocks#es-module-import%E3%82%92%E5%88%A9%E7%94%A8%E3%81%99%E3%82%8B): using ES module imports you would normally write import declarations at the top of your test files. However, you need to tell Jest to use mocks prior to the module using them. To do this, Jest automatically moves the jest.mock call to the beginning of the module (before you do the import).
    - I thought, "Shouldn't it be placed first?" but ESLint complains "Import in body of module; reorder to top."
    - I thought it would replace the imported one at the time of mock since it works afterwards, but that doesn't seem to be the case.
- I decided to do spyOn on top of it, since spyOn would certainly replace it at that time.
    - The test that the menu display is different depending on whether previousTalkID exists or not worked for a while.
    - However, I don't think I can determine if the menu actually doesn't exist or if the asynchronous redrawing has not yet finished.
        - I could wait until it times out to make a decision, but I don't want to do that because it would slow down the test.
ts

```typescript
  const { container } = render(<App />);
  expect(container).toMatchSnapshot();
  fireEvent.click(screen.getByLabelText("menu"));
  expect(screen.queryByText("Re-enter to Last Talk")).toBeNull();  // (1)

  jest
    .spyOn(managePreviousTalkIDModule, "getPreviousTalkID")
    .mockResolvedValue("test");
  render(<App />);
  await waitFor(() => screen.getByText("Re-enter to Last Talk"));

  expect(screen.queryByText("Re-enter to Last Talk")).not.toBeNull();
```


![image](https://gyazo.com/84b751a483459c1c05459b425c3d973e/thumb/1000)

- [[Wrapping in act in React tests is not render but state update]]
- [[When updating the state with the result of a Promise, it is not possible to wrap the entire Promise in an act]]

Next time "Why not replace useState with a mock?"

---
This page is auto-translated from [/nishio/Jestメモ Day3](https://scrapbox.io/nishio/Jestメモ Day3) using DeepL. If you looks something interesting but the auto-translated English is not good enough to understand it, feel free to let me know at [@nishio_en](https://twitter.com/nishio_en). I'm very happy to spread my thought to non-Japanese readers.