# 과제 과목
자료구조, project 2

# 과제 목적
project 2에서는 

# cygwin에서의 동작
### 컴파일 방법
cygwin 환경에서 'make' 명령어로 컴파일하고 './project2.exe' 명령어를 입력하여 프로그램을 실행할 수 있습니다. 이 때, 관련 파일들은 cygwin-home-user 폴더 위치에 관련 파일을 모두 저장해둔 상태여야 합니다. 실행하고 나면 아래와 같은 화면을 확인할 수 있습니다.
![image](https://github.com/user-attachments/assets/aa5a7d30-fb27-411c-bc25-e78eab889f5b)


### 실행 방법 예시
실행 방법의 예시는 아래와 같습니다.

1. Create a Tree: 실행화면에서 표시되어있는 번호의 기능 중 1을 입력하면 tree를 만듭니다. tree는 비어 있고, 이후 insertion을 통해 노드 추가가 가능해집니다.

2. Change BST to Array : 실행화면에서 표시되어있는 번호의 기능 중 2를 입력하면 현재 BST를 배열로 변환합니다. 변환된 array는 크기, 데이터를 포함하여 출력됩니다.

3. Build a Heap: 실행화면에서 표시되어있는 번호의 기능 중 3을 입력하면 주어진 array를 기반으로 min-heap을 생성합니다. 이런 식으로 만들어진 heap은 계층적 구조로 출력됩니다.

4. Delete the Heap: 실행화면에서 표시되어있는 번호의 기능 중 4를 입력하면 현재 heap을 delete합니다. 이후 heap은 삭제되어 더 이상 사용할 수 없게 되며 'Heap deleted successfully.'라고 출력됩니다.

5. Find the Depth of Heap: 실행화면에서 표시되어있는 번호의 기능 중 5를 입력하면 힙의 depth를 계산하여 'Depth of Heap is 4.'와 같은 형식으로 depth를 출력해냅니다.

6. Insert value to the Heap: 실행화면에서 표시되어있는 번호의 기능 중 6을 입력하고 추가할 값을 입력하면 heap에 새로운 값을 insert합니다.

7. Dequeue the Heap: 실행화면에서 표시되어있는 번호의 기능 중 7을 입력하면 heap의 루트 값을 제거하고 출력합니다.

8. Print the Heap: 실행화면에서 표시되어있는 번호의 기능 중 8을 입력하면 현재 heap의 모든 데이터를 계층적 구조로로 출력합니다.

9. Heap Sort: 실행화면에서 표시되어있는 번호의 기능 중 9를 입력하면 Heap Sort를 실행합니다. 주어진 array를 오름차순 정렬합니다.

10. Bubble Sort: 실행화면에서 표시되어있는 번호의 기능 중 10을 입력하면 Bubble Sort를 실행합니다. 주어진 array를 반복적으로 비교하여 오름차순 정렬합니다.

11. Insertion Sort: 실행화면에서 표시되어있는 번호의 기능 중 11을 입력하면 Insertion Sort을 실행합니다. 각 요소를 정렬된 위치로 삽입하며 array를 정렬합니다.

12. Selection Sort: 실행화면에서 표시되어있는 번호의 기능 중 12를 입력하면 Selection Sort를 실행합니다. array의 최소값을 반복적으로 선택하여 앞쪽에 배치합니다.

13. Quick Sort: 실행화면에서 표시되어있는 번호의 기능 중 13을 입력하면 Quick Sort를 실행합니다. 피벗을 기준으로 array를 나누어 정렬합니다.

14. Exit the program: 실행화면에서 표시되어있는 번호의 기능 중 0을 입력할 시 프로그램이 종료됩니다.


### 수정한 부분 및 함수 설명 (heap.c 파일)

##### create_tree()
이 함수는 비어 있는 새 binary tree를 만들어 return합니다. 새 binary tree는 루트가 NULL로 초기화되며 size는 0입니다.

##### create_node(int value)
이 함수는 value 값을 가지는 새 node를 만듭니다. 만들어진 node는 parent, left, right node 포인터가 모두 NULL로 초기화됩니다.

##### insert_node(struct tree* t, int value)
이 함수는 value 값을 BST의 맞는 위치에 insert합니다. tree를 탐색해 값에 따라서 작으면 왼쪽, 크면 오른쪽으로 이동하여 insert됩니다.

##### bstToArray(struct tree* t)
이 함수는 BST를 array로 변환합니다. 루트를 시작으로 array에 node 값을 저장하며, 이 때 array의 첫 번째 요소는 array 크기를 나타냅니다. 비어있는 node는 0으로 설정되어 있습니다.

##### bstToArrayRec(int* array, struct node* n, int index, int* maxI)
이 함수는 recursive하게 BST를 array로 변환할 때 사용합니다. 현재 node 값을 저장하고 왼쪽 자식 node는 2 * index + 1, 오른쪽 자식 node는 2 * index + 2 위치에 저장합니다.

##### createHeap()
이 함수는 새 binary heap을 만들어 반환합니다. heap의 size는 0으로 초기화됩니다.

##### printHeap(HEAP h)
이 함수는 heap.h의 내용을 출력하며, heap의 depth, size, 계층 구조를 모두 출력합니다. 

##### swap(int*n1, int*n2)
이 함수는 pointer를 이용하여 두 node를 swap합니다. 

##### buildHeap(HEAP* h, int* array, int arraySize)
이 함수는 주어진 array를 기반으로 min heap을 만듭니다. 만약 heap이 존재하지 않으면 에러 메시지를 출력하게 합니다. array의 절반 node부터 루트 방향으로 이동하면 각 node에 대해 min heap 조건을 유지할 수 있게 합니다. 

##### deleteHeap(HEAP h)
이 함수는 heap을 삭제하는 역할을 합니다. heap이 삭제되면 모든 메모리가 컴퓨터에 반환되어 다른 프로세스에서 사용할 수 있게 됩니다. heap이 성공적으로 삭제되었을 시 "Successfully deleted."가 출력되고, 그렇지 않으면 "Error : No heap exists."가 출력됩니다.

##### findDepth(HEAP h)
이 함수는 heap의 루트로부터 depth를 계산하여 반환합니다. heap의 size를 2로 반복적으로 나누어 depth를 결정합니다. 이 반환 값을 통해 main 함수는 Depth를 "Depth is: (the depth of tree)."를 출력하고, heap이 만들어지지 않았으면 "Error: No heap exists."를 출력합니다.

##### insertNode(HEAP h, int value)
이 함수는 heap에 새로운 노드를 추가합니다. 삽입할 값은 매개변수 value로 제공됩니다. 새로운 노드는 heap의 가장 아래 오른쪽 위치에 추가된 후, 부모 노드와 비교하여서 heap의 min heap 조건을 유지합니다. heap이 존재하지 않을 경우에는 "Heap does not exist."를 출력하고, 삽입 값이 1 이하일 경우 "Invalid value."를 출력합니다.

##### dequeueHeap(HEAP h)
이 함수는 heap의 루트 노드를 제거(dequeue)한 후 반환합니다. 제거 후에도 heap의 min heap을 유지하기 위한 과정을 수행합니다. heap이 생성되지 않았거나 비어 있는 경우, "Heap does not exist or is empty."를 출력하고 -1을 반환합니다. heap의 루트 값을 제거하고, 마지막 노드를 루트로 이동한 뒤 재정렬하여 min heap을 유지합니다.

##### heapSort(HEAP h, int* heapsort, int count)
이 함수는 heap sort를 통해 array를 정렬합니다. buildHeap 함수를 호출하여 입력 array를 기반으로 min heap을 생성한 후, dequeueHeap을 반복 호출하여 heap의 루트 값을 제거하면서 array에 정렬된 값을 저장합니다. heap 데이터는 정렬 과정에서 비워지며, 최종적으로 array에는 입력값이 오름차순 정렬됩니다.

##### bubbleSort(int* Array)
이 함수는 bubbleSort를 통해 array를 오름차순 정렬합니다. array 내 인접 요소를 반복 비교하고 교환하여 제일 큰 값을 뒤로 옮기는 방식으로 동작합니다. swap 함수를 통해 요소를 교환하며, array의 크기는 20으로 고정되어 있습니다. 이 함수는 main.c에서 이미 결정된 array를 입력받아 정렬합니다.

##### insertionSort(int* Array)
이 함수는 insertionSort를 통해 array를 오름차순 정렬합니다. 현재 요소를 key에 저장하고, 이전 요소들과 비교하며 더 큰 값은 오른쪽으로 이동시킨 뒤, key 값을 맞는 위치에 삽입합니다. array의 크기는 20으로 고정되어 있으며, 이 함수는 main.c에서 결정된 array를 입력받아 정렬합니다. 

##### selectionSort(int* Array)
이 함수는 selectionSort를 통해 array를 오름차순 정렬합니다. 각 반복에서 현재 위치를 기준으로 min 값의 인덱스를 찾고, 이를 현재 위치와 교환하여 정렬합니다. array의 크기는 20으로 고정되어 있으며, main.c에서 array가 입력됩니다. 

##### quickSort(int* Array, int low, int high)
이 함수는 quickSort 알고리즘을 구현하여 array를 오름차순 정렬합니다. 정렬할 array와 시작, 마지막 index인 low와 high를 매개변수로 받습니다. partition 함수는 피벗을 기준으로 array를 분할하며, 피벗보다 작은 값들은 왼쪽, 큰 값들은 오른쪽에 배치됩니다. 이 과정을 재귀적 반복해서 array를 정렬합니다. array의 크기는 20으로 고정돼 있으며, main.c에서 입력됩니다. 

##### printArray(int* Array)
이 함수는 입력된 array를를 출력합니다. array를 순회하며, 각 요소를 공백으로 구분하여 출력할 수 있게 합니다.





