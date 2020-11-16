# Java4
java实验四
## 实验目的
掌握Java中抽象类和抽象方法的定义； 
掌握Java中接口的定义，熟练掌握接口的定义形式以及接口的实现方法
了解异常的使用方法，并在程序中根据输入情况做异常处理
## 实验内容
某学校为了给学生提供勤工俭学机会，也减轻授课教师的部分压力，准许博士研究生参与课程的助教工作。此时，该博士研究生有双重身份：学生和助教教师。
设计两个管理接口：学生管理接口和教师管理接口。学生接口必须包括缴纳学费、查学费的方法；教师接口包括发放薪水和查询薪水的方法。
设计博士研究生类，实现上述的两个接口，该博士研究生应具有姓名、性别、年龄、每学期学费、每月薪水等属性。（其他属性及方法，可自行发挥）
编写测试类，并实例化至少两名博士研究生，统计他们的年收入和学费。根据两者之差，算出每名博士研究生的年应纳税金额（国家最新工资纳税标准，请自行检索）。
## 实验过程
1 创建系统，研究生一研究生二
2 利用函数interface创建学生管理接口和教师管理接口。
3 在接口利用函数find afford get建立缴纳学费、查学费、发放薪水和查询薪水。
4 改错并运行。
## 核心方法
```
public class hjh {

    public static void main(String[] args) {
        try {
            System.out.println("研究生一");
            Doctor hjh = new Doctor();
            hjh.setName("何佳航");
            hjh.setAge(20);
            hjh.setNumber(2019310866);
            hjh.setSex("男");
            hjh.setTuition(4500);
            hjh.setSalary(1000);
            System.out.println("学生姓名:" + hjh.getName());
            System.out.println("学生年龄:" + hjh.getAge());
            System.out.println("学生编号:" + hjh.getNumber());
            System.out.println("学生性别:" + hjh.getSex());
            hjh.find_tuition();
            hjh.find_salary();
            hjh.taxation();
            System.out.println("研究生二");
            Doctor wh = new Doctor();
            wh.setName("王红");
            wh.setAge(20);
            wh.setNumber(2019610321);
            wh.setSex("女");
            wh.setTuition(4500);
            wh.setSalary(100);
            System.out.println("学生姓名:" + wh.getName());
            System.out.println("学生年龄:" + wh.getAge());
            System.out.println("学生编号:" + wh.getNumber());
            System.out.println("学生性别:" + wh.getSex());
            wh.find_tuition();
            wh.find_salary();
            wh.taxation();
        } catch (Exception e) {
            System.out.println("数据异常");
        }

    }

    interface Manger_student {
        double find_tuition();

        double afford_tuition();
    }

    interface Manger_teacher {
        double STANDARD = 0.2;

        double find_salary();

        double get_salary();
    }


    public static class Doctor implements Manger_student, Manger_teacher {
        public Doctor() {

        }

        public Doctor(String name, int age, int number, String sex, double tuition, double salary) {
            this.name = name;
            this.age = age;
            this.number = number;
            this.sex = sex;
            this.tuition = tuition;
            this.salary = salary;
        }

        private String name;
        private int age;
        private int number;
        private String sex;
        private double tuition;
        private double salary;


        public void setName(String name) {
            this.name = name;
        }

        public void setAge(int age) {
            this.age = age;
        }

        public void setNumber(int number) {
            this.number = number;
        }

        public void setSex(String sex) {
            this.sex = sex;
        }

        public void setTuition(double tuition) {
            this.tuition = tuition;
        }

        public void setSalary(double salary) {
            this.salary = salary;
        }

        public String getName() {
            return name;
        }

        public int getAge() {
            return age;
        }

        public String getSex() {
            return sex;
        }

        public double getTuition() {
            return tuition;
        }

        public int getNumber() {
            return number;
        }

        public double getSalary() {
            return salary;
        }


        public double find_tuition() {
            System.out.println("每年学费：" + tuition);
            return tuition;
        }

        public double find_salary() {
            System.out.println("每月工资：" + salary);
            return salary;
        }

        public double afford_tuition() {
            System.out.println("缴纳成功，已缴纳学费" + tuition);
            return tuition;
        }

        public double get_salary() {
            double c;
            c = salary - (salary - 800) * STANDARD;
            System.out.println("薪水已经发放，发放金额：" + c);
            return salary;
        }

        public void taxation() {
            double a;
            a = 12 * ((salary - 800) * STANDARD);
            System.out.println("每年应纳税为：" + a);
        }
    }
}
 ```
 ## 实验结果
研究生一
姓名何佳航
年龄:20
编号:2019310866
性别:男
每年学费：4500
每月工资：1000.0
每年纳税为：480.0
研究生二
学生姓名:王红
学生年龄:20
学生编号:2019610321
学生性别:女
每年学费：4500
每月工资：100.0
每年纳税为：48.0

## 实验感想
这个系统是我独立完成在这次的课程设计中，我学到的一个重要的经验，参考一些资料后使程序设计更加简单，设计代码时目标更加明确，效率更高，以前虽然也知道这些道理，但自己真正使用时出现在问题，学会了创建接口程序，学会利用接口程序的函数，让我增加了对编程的兴趣。
