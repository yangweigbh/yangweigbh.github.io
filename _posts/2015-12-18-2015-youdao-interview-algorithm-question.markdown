---
layout: post
title:  "2015 有道云校招笔试试题(算法)"
categories: IT
---

# 2015 有道云校招笔试试题(算法)
> 在满足以下条件的前提下，手机解锁九宫格一共有多少种可能的解锁图案？
> 
> 条件一，解锁图案至少经过两个点
> 
> 条件二，经过的点不能有重复

解题思路还是采用穷举法，同时使用一个数组记录哪些格子已经遍历过了，见代码：

{% raw %}
```java

public class NineBlock {

    static class Count {
        int val = 0;
    }

    public static int solution() {
        boolean visited[][] = new boolean[3][3];
        Count count = new Count();
        for (int i = 2; i <= 9; i++) {
            for(int r = 0; r < 3; r++) {
                for (int c = 0; c < 3; c++) {
                    util(r, c, 1, i, count, visited);
                }
            }
        }
        return count.val;
    }

    private static void util(int r, int c, int curlen, int len, Count count, boolean[][] visited) {
        if (curlen == len) {
            count.val++;
            return;
        }
        visited[r][c] = true;
        int[][] dir = {{r-1, c-1}, {r-1, c}, {r-1, c+1}, {r, c-1}, {r, c+1},
                {r+1, c-1}, {r+1, c}, {r+1, c+1}, {r-2, c-1},
                {r-2, c+1}, {r-1, c-2}, {r-1, c+2},
                {r+1, c-2}, {r+1, c+2}, {r+2, c-1}, {r+2, c+1}};
        for (int i = 0; i < dir.length; i++) {
            if (valid(dir[i][0], dir[i][1]) && !visited[dir[i][0]][dir[i][1]]) {
                util(dir[i][0], dir[i][1], curlen+1, len, count, visited);
            }
        }
        visited[r][c] = false;
    }

    private static boolean valid(int i, int j) {
        if (i < 3 && i >= 0 && j < 3 && j >= 0) {
            return true;
        }
        return false;
    }

    public static void main(String[] args) {
        System.out.println(solution());
    }

}

```
{% endraw %}