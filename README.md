# 2020-12-28 (mon)
# 메서드 오버라이딩(Method overriding)


# 1. 클래스 유닛 생성

class unit:
    def __init__(self, name, hp, speed):
        self.name = name
        self.hp = hp
        self.speed = speed

    def move(self, location):
        print("[지상유닛이동]")
        print("{0} : {1} 방향으로 이동합니다. [속도 : {2}]".format(self.name,location,self.speed))



# 2. 클래스 어택유닛 생성

class attackunit(unit):
    def __init__(self, name, hp, speed, damage):
         unit.__init__(self, name, hp, speed) 
         self.damage = damage
         
         
         
# 3. 클래스 플라이어블 생성

class flyable:
    def __init__(self, flyingspeed):
        self. flyingspeed = flyingspeed

    def fly(self, name, location): 
        print("{0} : {1}방향으로 날아갑니다. [속도 : {2}] ".format(name,location, self.flyingspeed))



# 4. 클래스 플라이어블 어택 유닛 생성

class flyableattackunit(attackunit, flyable):
    def __init__(self, name, hp, damage, flyingspeed):
         attackunit.__init__(self, name, hp, 0, damage) 
         flyable.__init__(self, flyingspeed)

    def move(self, location)
         print("[공중유닛이동]")
         self.fly(self.name, location) 
         
         
 # a. 오늘의 개념: 여기서 메서드 오버라이딩이 출현!!
 # fly라는 부모 클래스(flyable)의 메서드 함수를 빌려오는 것 : move 함수는 이제 fly 함수의 기능을 대신 하거라~! 
 # fly 함수 써주고 전달값도 fly 함수형식에 맞게 전달해줌
 # 엄밀히 말하면 플라이어블 집안(=클래스) 메서드함수를 어택유닛 집안 메서드 함수에 빌려주는 것(지금 이 두 집안을 다 상속받아서 메서드 오버라이딩이 가능한거임)
 # b. 본인의 정리: a 클래스, b 클래스로 부터 다중 상속을 받았을 때, a 부모 클래스의 메서드 함수가 b 부모 클래스의 매서드 함수의 기능을 대신할 수 있음
 # c. 본인의 질문: 오버라이딩 하는 함수들끼리 전달값이 달라도 되네..? 궁금증이 풀림..



battle = flyableattackunit(battle.name,500, 25, 3)
battle.move("9시")
 # 이제 move 함수를 써도 fly 함수의 결과를 생성해내는 걸 볼 수 있음!
