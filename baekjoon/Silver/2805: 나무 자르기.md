2805: 나무 자르기

'''python
import sys
input = sys.stdin.readline

n, m = map(int, input().split())
trees = list(map(int, input().split()))

trees_sum = sum(trees)
trees_min = 1
trees_max = max(trees)

while trees_max >= trees_min:
    height = (trees_min+trees_max)//2
    cuts = 0
    for i in range(n):
        if trees[i] > height:
            cuts += trees[i]-height
    if cuts >= m:
        trees_min = height+1
    else:
        trees_max = height-1

print(trees_max)
'''
