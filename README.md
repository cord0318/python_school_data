# SCHOOLπ±

νμ΄μ¬μ© νμ νκ΅ λ°μ΄ν° λΌμ΄λΈλ¬λ¦¬ μλλ€.

- https://pypi.org/project/school_data
- https://github.com/cord0318/python_school_data

## π₯λ€μ΄λ‘λ

μλμ°λ λ¦¬λμ€μ ν°λ―Έλμμ λ€μκ³Ό κ°μ΄ μλ ₯ν©λλ€.

```shell
pip install school_data
```

μ€λ₯κ° λλ κ²½μ°, `python -m pip install --upgrade pip` λ‘ pipλ₯Ό μλ°μ΄νΈ ν΄μ£ΌμΈμ.

## π€μ¬μ©λ²

λμ΄μ€ μλ²μ ν΅μ νλ κΈ°λ₯μ΄κΈ° λλ¬Έμ, λΉλκΈ° μ²λ¦¬λ₯Ό μΆμ²λλ¦½λλ€.

1. νκ΅ κΈμ
```python
# λκΈ°
import school
school.meal_data("B10", "7081423")

#school_meal_data("μ§μ­μ½λ", "νκ΅μ½λ", "κΈμ μ½λ", "λ μ§")
```

```python
# λΉλκΈ°
import asyncio
import school
async def main():
    await school.asyncMealData("μ§μ­μ½λ", "νκ΅μ½λ", "κΈμ μ½λ", "λ μ§")
asyncio.get_event_loop().run_until_complete(main())
```

```python
# ν ν° κΈ°λ₯
# λκΈ°
import school
token = school.MealToken("νκ΅μ΄λ¦")
data = school.MealTokenCheck(token["token"], "λ μ§")
print(data)
```

```python
# ν ν° κΈ°λ₯
# λΉλκΈ°
import asyncio
import school
async def main():
    token = await school.asyncMealToken("νκ΅μ΄λ¦")
    data = await school.asyncMealTokenCheck(token['token'], "λ μ§")
    print(data)
```

2. νκ΅ μ λ³΄
```python
# νκ΅ μ λ³΄
# λκΈ°
import school
data = school.school_data("νκ΅μ΄λ¦")
print(data)
```

```python
# νκ΅ μ λ³΄
# λΉλκΈ°
import asyncio
import school
async def main():
    data = await school.asyncSchoolData("νκ΅μ΄λ¦")
    print(data)
```

3. νκ΅ μκ°ν
!! μ΄ κΈ°λ₯μ μ€λ₯κ° λ§μ΅λλ€ (νμ¬ κ°λ°μ€) !!
```python
# νκ΅ μκ°ν
# λκΈ°
import school
data = school.SchoolSchedule("νκ΅νμ", "μ§μ­μ½λ", "νκ΅μ½λ", "νλ", "λ°", "κ΅μ(μ ν)", "λ μ§")
# νκ΅νμ λͺ©λ‘: ["elsTimetable", "misTimetable", "hisTimetable", "spsTimetable", "els", "mis", "his", "sps", "μ΄λ±", "μ€λ±", "κ³ λ±", "νΉμ", "μ΄λ±νκ΅", "μ€νκ΅", "κ³ λ±νκ΅", "νΉμνκ΅"]
print(data)
```

```python
# νκ΅ μκ°ν
# λΉλκΈ°
import asyncio
import school
async def main():
    data = await school.asyncSchoolSchedule("νκ΅ νμ", "μ§μ­μ½λ", "νκ΅μ½λ", "νλ", "λ°", "κ΅μ(μ ν)", "λ μ§")
    # νκ΅νμ λͺ©λ‘: ["elsTimetable", "misTimetable", "hisTimetable", "spsTimetable", "els", "mis", "his", "sps", "μ΄λ±", "μ€λ±", "κ³ λ±", "νΉμ", "μ΄λ±νκ΅", "μ€νκ΅", "κ³ λ±νκ΅", "νΉμνκ΅"]
    print(data)
```

```python
# νκ΅ μκ°ν
# λκΈ°
# ν ν°
import school
token = school.ScheduleToken("νκ΅νμ", "νκ΅μ΄λ¦", "νλ", "λ°")
data = school.ScheduleTokenCheck(token['token'], "κ΅μ(μ ν)", "λ μ§")
print(data)
```

```python
# νκ΅ μκ°ν
# λΉλκΈ°
# ν ν°
import asyncio
import school
async def main():
    token = await school.asyncScheduleToken("νκ΅νμ", "νκ΅μ΄λ¦", "νλ", "λ°")
    data = await school.asyncScheduleTokenCheck(token['token'], "κ΅μ(μ ν)", "λ μ§")
```

## β©οΈλ¦¬ν΄κ°

λͺ¨λ  λ¦¬ν΄κ°μ Dict λ‘ λ°νλ©λλ€.

```python
{"error":Boolen(True,False),"code":"μ²λ¦¬μ½λ(λ°μ μ²λ¦¬μ½λ μ’λ₯ μ°Έμ‘°)","message":"ν΄λΉ μλ¬λ, μ±κ³΅ μν©μ λν μ€λͺ",......}
```
