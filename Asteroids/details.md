# Asteroids
Your planet is a perfect sphere with radius R and center at (0, 0, 0). There are N asteroids around the planet. Your task is to find the minimal possible number of asteroids you can observe from some point on the suface of the planet. An asteroid can be observed if it's at least 10-3 above the horizon line at the place of the observation.
## Input
The first line of input contains a single integer T, denoting the number of testcases.

The first line of each test case contains two space-separated integers, N and R.

The following N lines contains 3 space-separated integers each: coordinates xi, yi, zi of the corresponding asteroid. 
## Output
For each test case, output one integer in a new line: the answer for the test case.
## Constraints
- 1 ≤ T ≤ 10
- 1 ≤ R ≤ 10
- R - 1 ≤ |xi|, |yi|, |zi| ≤ 50
- Subtask 1[11 points]: 1 ≤ N ≤ 2
- Subtask 2[89 points]: 1 ≤ N ≤ 150
## Example
### Input:
    1
    3 1
    2 2 2
    0 3 4
    4 5 0

### Output:
    0
## Sample explanation:
One of the solutions can be: as all the asteroids have positive coordinates, we can choose some point on the surface which lies in the all-negative octant, and none of the asteroids will be observed. 
