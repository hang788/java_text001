
import java.util.ArrayList;
import java.util.Scanner;


public class mainSysteam {
    public static void main(String[] args) {
        System.out.println("-------------欢迎来到我的学生管理系统-------------");
        menu();
        ArrayList<Student> list = new ArrayList<>();
        while (true) {
            Scanner sc = new Scanner(System.in);
            String choose = sc.next();
            switch (choose) {
                case "1" -> {
                    System.out.println("添加学生");
                    addStudent(list);
                    menu();
                }
                case "2" -> {
                    System.out.println("删除学生");
                    delStudent(list);
                    menu();
                }
                case "3" -> {
                    System.out.println("修改学生");
                    reviseStudent(list);
                    menu();
                }
                case "4" -> {
                    {
                        System.out.println("查询学生");
                        findStudent(list);
                        menu();
                    }
                }
                case "5" -> {
                    System.out.println("退出");
                    System.exit(0);
                    menu();
                }
                default -> System.out.println("没有这个选项");
            }
        }

    }

    // 菜单的实现
    public static void menu() {
        System.out.println("1:添加学生");
        System.out.println("2:删除学生");
        System.out.println("3:修改学生");
        System.out.println("4:查询学生");
        System.out.println("5:退出");
        System.out.println("请输入您的选择:");
    }

    //1.添加学生
    public static ArrayList<Student> addStudent(ArrayList<Student> list) {
        Student student = new Student();
        Scanner sc = new Scanner(System.in);
        System.out.println("请输入学生id");
        String id = sc.next();
        while (idOne(list, id) >= 0) {
            System.out.println("id存在请重新输入");
            id = sc.next();
        }
        student.setId(id);
        System.out.println("请输入学生姓名");
        student.setName(sc.next());
        System.out.println("请输入学生年龄");
        student.setAge(sc.nextInt());
        System.out.println("请输入学生地址");
        student.setAddress(sc.next());
        list.add(student);
        System.out.println("删除成功");
        return list;
    }

    //判断id号码是否存在,如果存在则返回其下标，没有则返回-1
    public static int idOne(ArrayList<Student> list, String id) {
        for (int i = 0; i < list.size(); i++) {
            if (list.get(i).getId().equals(id)) {
                return i;
            }
        }
        return -1;
    }

    //2.删除学生
    public static ArrayList<Student> delStudent(ArrayList<Student> list) {
        System.out.println("请输入你要删除学生的id号码");
        Scanner sc = new Scanner(System.in);
        String id = sc.next();
        int idex = idOne(list, id);
        if (idex >= 0) {
            list.remove(idex);
            System.out.println("删除成功");
        } else {
            System.out.println("输入的id号码错误");
        }
        return list;
    }

    //3:修改学生
    public static ArrayList<Student> reviseStudent(ArrayList<Student> list) {
        System.out.println("请输入你要修改学生的id号码");
        Scanner sc = new Scanner(System.in);
        String id = sc.next();
        int idex = idOne(list, id);
        if (idex >= 0) {
            Student student = list.get(idex);
            System.out.println("你要修改的学生信息如下");
            System.out.println(student.getId() + "," + student.getName() + ","
                    + student.getAge() + "," + student.getAddress());
            System.out.println("请输入你改后的id值，如果不修改则输入-1");
            String changeId = sc.next();
            if (!changeId.equals("-1")) {
                student.setId(changeId);
            }

            System.out.println("请输入你你改后的名字，如果不修改则输入-1");
            String changeName = sc.next();
            if (!changeName.equals("-1")) {
                student.setName(changeName);
            }
            System.out.println("请输入你要修改后的年龄，如果不修改则输入-1");
            int changeAge = sc.nextInt();
            if (changeAge != -1) {
                student.setAge(changeAge);
            }
            System.out.println("请输入你要修改后的地址，如果不修改则输入-1");
            String changeAddress = sc.next();
            if (!changeAddress.equals("-1")) {
                student.setAddress(changeAddress);
            }
            System.out.println("修改成功");
        } else {
            System.out.println("输入的id号码错误");
        }
        return list;
    }


    //4.查询学生
    public static void findStudent(ArrayList<Student> list) {
        System.out.println("请输入你要查询学生的id号码");
        Scanner sc = new Scanner(System.in);
        String id = sc.next();
        int idex = idOne(list, id);
        if (idex >= 0) {
            Student student = list.get(idex);
            System.out.println(student.getId() + "," + student.getName() + ","
                    + student.getAge() + "," + student.getAddress());
        } else {
            System.out.println("输入的id号码错误");
        }
    }

}

