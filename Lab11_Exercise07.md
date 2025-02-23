# Lab 11 Exercise 7

## Prevent inheritance by keyword `sealed`

1.สร้าง console application project

```cmd
dotnet new console --name Lab11_Ex07
```
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/beb61e21-a03f-480e-9c6b-74f2e3ba1931)

2.เปลี่ยน code ให้เป็นดังต่อไปนี้

```cs
Derived_2 d2 = new Derived_2();
Base b = (Base) d2;
Derived_1 d1 = (Derived_1) d2;

b.A();
d1.A();
d2.A();

class Base
{
    public virtual void A()
    {
        System.Console.WriteLine("Base.A()");
    }
}
class Derived_1 : Base
{
    public sealed override void A()
    {
        System.Console.WriteLine("Derived_1.A()");
    }
}
class Derived_2 : Derived_1
{
    public override void A()
    {
        System.Console.WriteLine("Derived_2.A()");
    }
}
```
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/24875100-90a3-4b79-9447-d08543e44211)



3.Build project โดยการใช้คำสั่ง

```cmd
dotnet build  Lab11_Ex07
```

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง

4.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 3

![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/516c7e3c-b1e8-4810-b2a4-1d4d8d79da14)

5.Run project โดยการใช้คำสั่ง

```cmd
dotnet run --project Lab11_Ex07
```

6.บันทึกผลที่ได้จากการรันคำสั่งในข้อ 5
![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/56bf499c-dcbf-4a2d-bceb-5cd8ee7d935c)

ถ้ามีที่ผิดพลาดในโปรแกรม ให้แก้ไขให้ถูกต้อง


![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/5b1c1efc-cad5-479c-9213-ef92ae4ed903)

![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/c8a0f286-20d7-4e98-bedf-df677fafc24d)

![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/00648e5c-15e0-457e-8900-a46d338266eb)


![ภาพ](https://github.com/AnchisaPhetnoi/03376836-OOP-2566-Lab-11/assets/144197034/275bf6c3-f897-4166-b8b1-d2edb4b3b0e4)


7.อธิบายสิ่งที่พบในการทดลอง
จากการทดลอง พบว่าโค้ด มีข้อผิดพลาดบางอย่าง เมื่อทำการแก้ไขแล้วจะได้โค้ดังนี้
เรามีโค้ดที่สร้างขึ้นเพื่อทดสอบการใช้งานการสืบทอดคลาสและการโอเวอร์ไรด์เมทอดใน C#
เริ่มต้นที่ Main method ซึ่งสร้างอ็อบเจกต์ d2 จากคลาส Derived_2 และทำการแปลงให้เป็นอ็อบเจกต์ของคลาส Base และ Derived_1 โดยใช้การ casting

เมื่อเรียกใช้งานเมทอด A() บนอ็อบเจกต์ b และ d1 ซึ่งเป็นอ็อบเจกต์ของคลาส Base และ Derived_1 ตามลำดับ จะเรียกใช้งานเมทอด A() ที่ถูกโอเวอร์ไรด์ในคลาสลูก.

เมื่อเรียกใช้งานเมทอด A() บนอ็อบเจกต์ d2 ซึ่งเป็นอ็อบเจกต์ของคลาส Derived_2 ผลลัพธ์ที่คาดหวังคือการเรียกใช้งาน A() ที่ถูกโอเวอร์ไรด์ในคลาส Derived_2.

ผลลัพธ์คือการแสดงผลลัพธ์ "Base.A()", "Derived_1.A()", และ "Derived_2.A()" ตามลำดับ เนื่องจากการโอเวอร์ไรด์เมทอดและลำดับการแปลงชนิดทำให้เมทอดที่ถูกเรียกใช้งานเป็นเมทอดของคลาสที่เหมาะสมในแต่ละกรณี ตามลำดับที่เราได้กำหนดไว้ในโค้ดการทดลองนี้ 

ดังผลลัพธ์ ภาพด้านบน

