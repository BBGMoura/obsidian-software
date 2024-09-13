## Question
Given an array of `intervals` where `intervals[i] = [starti, endi]`, merge all overlapping intervals, and return _an array of the non-overlapping intervals that cover all the intervals in the input_.

**Example 1:**

**Input:** intervals = [[1,3],[2,6],[8,10],[15,18]]
**Output:** [[1,6],[8,10],[15,18]]
**Explanation:** Since intervals [1,3] and [2,6] overlap, merge them into [1,6].

**Example 2:**

**Input:** intervals = [[1,4],[4,5]]
**Output:** [[1,5]]
**Explanation:** Intervals [1,4] and [4,5] are considered overlapping.

**Constraints:**

- `1 <= intervals.length <= 104`
- `intervals[i].length == 2`
- `0 <= starti <= endi <= 104`


## Solution - Sorting
**How can we tell that the intervals are overlapping?**
- is the end of the first interval inside the second interval range
- is the beginning interval overlapping the second interval range

If we sort the intervals by their `start` value, then each set of intervals can be merged will appear as a contiguous run in the sorted list.

In this case, if the starting position of the second interval is within the range of the current interval, we can merge these.


``` java
public int[][] merge(int[][] intervals) {
	Arrays.sort(intervals -> Comperator.comparingInt(a -> a[0]));

	LinkedList<int[]> merged = new LinkedList<>();

	for (int[] range : intervals)  {
		if (merged.isEmpty() || range[0] > merged.getLast()[1]) {
			merged.add(range);
		} else {
			merged.getLast()[1] = Math.max(range[1], merged.getLast()[1]);
		}
	}
	return merged.toArray(new int[merge.size()][]);
}
```