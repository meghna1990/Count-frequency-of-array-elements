#include <stdio.h>

int main() {
    int arr[] = {1, 2, 2, 3, 1, 4, 2, 3};
    int n = sizeof(arr) / sizeof(arr[0]);
    int visited[n];

    for (int i = 0; i < n; i++) {
        visited[i] = 0; // mark all as unvisited
    }

    printf("Element frequencies:\n");
    for (int i = 0; i < n; i++) {
        if (visited[i] == 1) continue; // already counted

        int count = 1;
        for (int j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                visited[j] = 1;
                count++;
            }
        }
        printf("%d : %d\n", arr[i], count);
    }

    return 0;
}
OUTPUT
Element frequencies:
1 : 2
2 : 3
3 : 2
4 : 1
PYTHON
arr = [1, 2, 2, 3, 1, 4, 2, 3]

frequency = {}

for num in arr:
    frequency[num] = frequency.get(num, 0) + 1

print("Element frequencies:")
for key, value in frequency.items():
    print(key, ":", value)
OUTPUT
Element frequencies:
1 : 2
2 : 3
3 : 2
4 : 1
# Count-frequency-of-array-elements
