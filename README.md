# SCHOOL📱

파이썬용 학생 학교 데이터 라이브러리 입니다.

- https://pypi.org/project/school_data
- https://github.com/cord0318/python_school_data

## 📥다운로드

윈도우나 리눅스의 터미널에서 다음과 같이 입력합니다.

```shell
pip install school_data
```

오류가 나는 경우, `python -m pip install --upgrade pip` 로 pip를 업데이트 해주세요.

## 🤖사용법

나이스 서버와 통신하는 기능이기 때문에, 비동기 처리를 추천드립니다.

1. 학교 급식
```python
# 동기
import school
school.meal_data("B10", "7081423")

#school_meal_data("지역코드", "학교코드", "급식 코드", "날짜")
```

```python
# 비동기
import asyncio
import school
async def main():
    await school.asyncMealData("지역코드", "학교코드", "급식 코드", "날짜")
asyncio.get_event_loop().run_until_complete(main())
```

```python
# 토큰 기능
# 동기
import school
token = school.MealToken("학교이름")
data = school.MealTokenCheck(token["token"], "날짜")
print(data)
```

```python
# 토큰 기능
# 비동기
import asyncio
import school
async def main():
    token = await school.asyncMealToken("학교이름")
    data = await school.asyncMealTokenCheck(token['token'], "날짜")
    print(data)
```

2. 학교 정보
```python
# 학교 정보
# 동기
import school
data = school.school_data("학교이름")
print(data)
```

```python
# 학교 정보
# 비동기
import asyncio
import school
async def main():
    data = await school.asyncSchoolData("학교이름")
    print(data)
```

3. 학교 시간표
!! 이 기능은 오류가 많습니다 (현재 개발중) !!
```python
# 학교 시간표
# 동기
import school
data = school.SchoolSchedule("학교타입", "지역코드", "학교코드", "학년", "반", "교시(선택)", "날짜")
# 학교타입 목록: ["elsTimetable", "misTimetable", "hisTimetable", "spsTimetable", "els", "mis", "his", "sps", "초등", "중등", "고등", "특수", "초등학교", "중학교", "고등학교", "특수학교"]
print(data)
```

```python
# 학교 시간표
# 비동기
import asyncio
import school
async def main():
    data = await school.asyncSchoolSchedule("학교 타입", "지역코드", "학교코드", "학년", "반", "교시(선택)", "날짜")
    # 학교타입 목록: ["elsTimetable", "misTimetable", "hisTimetable", "spsTimetable", "els", "mis", "his", "sps", "초등", "중등", "고등", "특수", "초등학교", "중학교", "고등학교", "특수학교"]
    print(data)
```

```python
# 학교 시간표
# 동기
# 토큰
import school
token = school.ScheduleToken("학교타입", "학교이름", "학년", "반")
data = school.ScheduleTokenCheck(token['token'], "교시(선택)", "날짜")
print(data)
```

```python
# 학교 시간표
# 비동기
# 토큰
import asyncio
import school
async def main():
    token = await school.asyncScheduleToken("학교타입", "학교이름", "학년", "반")
    data = await school.asyncScheduleTokenCheck(token['token'], "교시(선택)", "날짜")
```

## ↩️리턴값

모든 리턴값은 Dict 로 반환됩니다.

```python
{"error":Boolen(True,False),"code":"처리코드(밑의 처리코드 종류 참조)","message":"해당 에러나, 성공 상황에 대한 설명",......}
```
