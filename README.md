# 문제 이해하기
## INPUT
  -배열(int(정수)) nums
  -int값(정수) target

## 설명
  배열 nums와 int값 target을 받았을 시, 배열 nums의 값 중 2택시 합이 target의 값과 같아질시 그 2택의 2개의 정수를 반환함
  (같은 값 2번 사용 불가능)

## 설명
  1. 배열, 정수값을 받음
  2. 배열의 값 중 2택 시 입력한 정수값이 되는지 확인
  3. 조건 통과시 그때의 배열의 값 2개를 반환
  
# 문제 풀이  
#include <iostream>
#include <vector> // vector 배열 헤더 추가
using namespace std;
// 참고 https://m.blog.naver.com/PostView.naver?isHttpsRedirect=true&blogId=jydev&logNo=220687965799

** c++
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) { // 1번 입력 = 베열, 2번 입력 = 기준값
        for (int a = 0; a < nums.size(); a++) { // 배열 0번부터 점검 시작, 배열 사이즈만큼 반복하며, 배열값을 늘려간다.
            for (int b = a + 1; b < nums.size(); b++) {// 2중 for문으로 계단식 점검 실행 => 1.1 1.2 1.3 -> 2.3 2.4 .......
                if (nums[a] + nums[b] == target) // 조건 검사 후
                    return { a, b }; // 반환
            }
        }
        return {}; // ???
    }
};
**

2중 for문을 사용한 계단식 조건 해결법 사용
이를 활용하여 조건에 맞는 값 2개를 반환.
