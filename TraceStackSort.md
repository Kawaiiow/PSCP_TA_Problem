# TraceStackSort

**Difficulty:** 2

## โปรแกรมที่เราได้รับมาเป็นโปรแกรมที่จะพยายามเรียงเลขจากน้อยไปมากโดยที่มีคุณลักษณะคือ

* ### โปรแกรมนี้มี **stack** 2 ชุด ที่ใช้สำหรับในการจัดเก็บตัวเลขจำนวนเต็ม แบ่งเป็น stack A และ B
  #### ข้อมูลเพิ่มเติมเกี่ยวกับ [stack](https://www.borntodev.com/2023/09/26/stack-%E0%B9%81%E0%B8%A5%E0%B8%B0-queue/)

* ### เลขที่รับเข้าโปรแกรมจะต้องไม่มีเลขซ้ำกัน
  
* ### ชุดเลขเริ่มต้นที่รับค่ามาจะถูกนำเข้า stack โดยเรียงจากตัวสุดท้ายไปยังตัวแรก (เลขตัวแรกจะอยู่ด้านบนสุดของ stack)

	#### Exmaple
	Input

	```5 2 3 1 -5 6```

	Stack

	![alttext](https://42-cursus.gitbook.io/~gitbook/image?url=https%3A%2F%2F2977649544-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fz2zo8aAL0o31034sj7J7%252Fuploads%252Fij5SIDHSSvOhHj92oJ33%252Fimage.png%3Falt%3Dmedia%26token%3D69c35151-c512-4f44-8eb6-19cc22f1b607&width=768&dpr=2&quality=100&sign=8c98c5dc&sv=2)

* ### โปรแกรมจะมีชุดคำสั่งที่ใช้ในการจัดเรียงตัวเลขทั้งหมด 11 คำสั่ง ดังนี้

	#### ตัวอักษรตัวสุดท้ายในคำสั่งคือตัวบอกว่าทำคำสั่งนี้ที่ stack A หรือ B

	เช่น sa ก็คือการทำ swap ที่ stack A

	### sa / sb / ss

	ทำการสลับเลข 2 ตัวแรกใน stack

	**ss คือการทำทั้ง sa และ sb**
	![alttext](https://42-cursus.gitbook.io/~gitbook/image?url=https%3A%2F%2F2977649544-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fz2zo8aAL0o31034sj7J7%252Fuploads%252FSmQJOlQjeGF7H2Ea3cCZ%252Fimage.png%3Falt%3Dmedia%26token%3D74c476b3-cf8b-4d19-b259-06258bde8d8c&width=768&dpr=2&quality=100&sign=47194cb9&sv=2)

	### pa / pb

	นำตัวเลขจากด้านบนสุดของอีก stack มาไว้ด้านบนสุดที่ stack ที่เรียก (เช่น pa จำเป็นการนำเลขด้านบนสุดของ stack B มาไว้ที่ด้านบนสุดของ stack A)
	![alttext](https://42-cursus.gitbook.io/~gitbook/image?url=https%3A%2F%2F2977649544-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fz2zo8aAL0o31034sj7J7%252Fuploads%252FALXRgodpBgdEsxRjTOad%252Fimage.png%3Falt%3Dmedia%26token%3D99d46e23-7cb5-403b-afd0-104ec0f3bba2&width=768&dpr=2&quality=100&sign=d552bb56&sv=2)

	### ra / rb / rr

	นำเลขด้านบนสุดของ stack ไปไว้ที่ด้านล่างสุดของ stack (เลขอื่นๆใน stack จะถูกดันขึ้นมาแทน)

	**rr คือการทำทั้ง ra และ rb**
	![alttext](https://42-cursus.gitbook.io/~gitbook/image?url=https%3A%2F%2F2977649544-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fz2zo8aAL0o31034sj7J7%252Fuploads%252FsiB3DTRrSAJF8nQ0hK8X%252Fimage.png%3Falt%3Dmedia%26token%3D89843cc8-6d97-4f2b-8787-1a1f258b8ae6&width=768&dpr=4&quality=100&sign=f1d00fab&sv=2)

	### rra / rrb / rrr
	
	นำเลขจากด้านล่างสุดของ stack ขึ้นมาด้านบนสุดของ stack (เลขอื่นๆใน stack จะถูกดันลง)
	
	**rrr คือการทำทั้ง rra และ rrb**
	![alttext](https://42-cursus.gitbook.io/~gitbook/image?url=https%3A%2F%2F2977649544-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252Fz2zo8aAL0o31034sj7J7%252Fuploads%252FKwUZNTLjTFmig6ioU3Jf%252Fimage.png%3Falt%3Dmedia%26token%3D55e18d0c-5d8a-482c-9d60-4dd4e879e88e&width=768&dpr=2&quality=100&sign=ae44f5ca&sv=2)

	#### ในการทำ 1 คำสั่งโปรแกรมจะพิมพ์ตัวคำสั่งออกมาด้วย 1 ครั้ง เมื่อจบโปรแกรมจะพิมพ์ Finish ออกมา

* ### เมื่อจบโปรแกรมตัวเลขจะต้องเรียงกันจากน้อยไปมากทั้งหมดใน stack A (หัวไปท้าย)

* ### หากมีคำสั่งที่แปลปลอมนอกเหนือจากนี้โปรแกรมจะยังสามารถส่งคำสั่งออกมาได้แต่จะถือว่าโปรแกรมเกิด Error แม้ว้าผลลัพธ์จากคำสั่งก่อนทั้งหมดจะถูกต้อง

โปรแกรมนี้มีอยู่มากหลายเวอร์ชั่น อยากให้เราช่วยเขียนโปรแกรมที่แสดงผลข้อมูลภายใน stack A และ B หลังจบการทำงานของคำสั่งทั้งหมด และตรวจสอบว่าผลลัพธ์ถูกต้องหรือไม่
หากเกิด Error ให้พิมพ์ Error ออกมา

# Input

- 1 บรรทัด: List ของชุดตัวเลขจำนวนเต็มที่เริ่มต้นในโปรแกรม (จำนวนเต็มบวก)
- n บรรทัด: คำสั่งการทำงานของโปรแกรม
- 1 บรรทัด: Finish

# Output

- 1 บรรทัด: ความถูกต้องของผลลัพธ์โปรแกรม Correct ,Incorrect หรือ Error
- 1 บรรทีด: ข้อมูลใน stack A
- 1 บรรทีด: ข้อมูลใน stack B
