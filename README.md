import string
# Foydalanuvchidan parol kiritishni so‘raymiz
parol = input("Parolni kiriting: ").strip()  
xatolar = []  # bo'sh list
# 1. Uzunlik: kamida 8 ta belgi bo‘lishi kerak
if len(parol) < 8:
    xatolar.append("Parol kamida 8 ta belgidan iborat bo'lishi kerak.")
# 2. Katta harf mavjudligini tekshirish
if not any(belgi.isupper() for belgi in parol):
    xatolar.append("Parolda kamida bitta KATTA harf bo'lishi kerak.")
# 3. Kichik harf mavjudligini tekshirish
if not any(belgi.islower() for belgi in parol):
    xatolar.append("Parolda kamida bitta kichik harf bo'lishi kerak.")
# 4. Raqam mavjudligini tekshirish
if not any(belgi.isdigit() for belgi in parol):
    xatolar.append("Parolda kamida bitta raqam bo'lishi kerak.")
# 5. Maxsus belgi mavjudligini tekshirish
maxsus_belgilar = set(string.punctuation)
if not any(belgi in maxsus_belgilar for belgi in parol):
    xatolar.append("Parolda kamida bitta maxsus belgi bo'lishi kerak (masalan: !,@,#,$,%, va hokazo).")
# Natijani chiqarish
if len(xatolar) == 0:
    print(" Parol qabul qilindi — barcha shartlar bajarilgan.")
else:
    print(" Parolda quyidagi kamchilik(lar) bor:")
    for i, xato in enumerate(xatolar, 1):
        print(f"{i}. {xato}")
