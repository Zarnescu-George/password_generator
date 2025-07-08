import random 
c = list(
    "ABCDEFGHIJKLMNOPQRSTUVWXYZ"
    "abcdefghijklmnopqrstuvwxyz"
    "0123456789"
    "!\#$%&*"
)
def generator() :
   password = ""
   for x in range (12):
      if( x % 4 == 0 and x != 0) :
           password += "-"
      password += random.choice(c)
   return password

def verify(password) :
    has_upper = any(c.isupper() for c in password)
    has_lower = any(c.islower() for c in password)
    has_digit = any(c.isdigit() for c in password)
    has_special = any(c in "!\#$%&*" for c in password)
    if(has_lower and has_upper and has_digit and has_special): v=1
    else : v=0
    return v

while True :
    test = generator()
    if(verify(test)):
        break

print("PASSWORD : ",test)
