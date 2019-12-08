计181 赵擎宇 2018310731
# 一、实验目的
分析学生选课系统。使用GUI窗体及其组件设计窗体界面。完成学生选课过程业务逻辑编程。基于文件保存并读取数据。处理异常。
# 二、实验要求
## 1、设计GUI窗体，支持学生注册、课程新加、学生选课、学生退课、打印学生选课列表等操作。
## 2、基于事件模型对业务逻辑编程，实现在界面上支持上述操作。
## 3、针对操作过程中可能会出现的各种异常，做异常处理
## 4、基于输入/输出编程，支持学生、课程、教师等数据的读写操作。
## 5、基于Github.com提交实验，包括实验SRC源文件夹程序、README.MD实验报告文档。
# 三、实验过程
建立新的类GUI，通过调用之前的crouse、Student和All的类进行对GUI的编辑。运用各种窗口组件，对GUI窗口进行布局的调整。建立各个不同的组件，给各个不同的组件进行赋值。然后在容器中引用他们。最后在文本框中输出要输出的内容。新建课程文件来储存课程的信息，在用户选择课程后再从文件中提取相应的内容，写到新建的另一个文件。将用户所输入的信息储存到文件中。
# 四、流程图
![image]()
# 五、核心代码
## 1，GUI
public gui(){
		super("学生选课");
		label1=new JLabel("请输入个人信息和所选课程，完成后单击确定，退出请按取消 ");
		label7=new JLabel("请输入开设的课程和信息，完成后单击确定，退出请按取消。");
		label2=new JLabel("学生姓名：");
		label8=new JLabel("教师姓名：");
		label3=new JLabel("性别:"); 
		cg = new CheckboxGroup(); 
		label9=new JLabel("课程名称：");
		label6=new JLabel("学号：");
		 label5=new JLabel("课程：");
		label11=new JLabel("上课地点：");
		label12=new JLabel("编号：");
		label13=new JLabel("学分：");
		c1=new JCheckBox("java");
		c2=new JCheckBox("高数");
		c3=new JCheckBox("python");
		c4=new JCheckBox("电路");
		ta1=new TextArea(17,20);
		ta2=new TextArea(17,20);
		button1=new JButton("确定");
		button2=new JButton("取消");
		button3=new JButton("确定");
		button4=new JButton("取消");
		t1=new JTextField("",5);
		t2=new JTextField("",10);
		t3=new JTextField("",5);
		t4=new JTextField("",5);
		t5=new JTextField("",5);
		t6=new JTextField("",5);
		t7=new JTextField("",5);
		t8=new JTextField("",5);
		t9=new JTextField("",5);
		t10=new JTextField("",5);
		setBounds(600,300,640,600);
		try {UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());
		}catch(Exception e){}
		c=getContentPane();	
		c.setBackground(Color.white);
		c.setLayout(new FlowLayout(FlowLayout.LEFT));
		c.add(label1);
		c.add(new JLabel("                       "));
		c.add(label7);
		c.add(new JLabel("                          "));
		c.add(label2);
		c.add(t1);
		c.add(label3);
		c.add(new Checkbox("男", cg, true)); 
		c.add(new Checkbox("女", cg, false));
		c.add(new JLabel("           "));
		c.add(label8);
		c.add(t3);
		c.add(new JLabel("                  "));
		c.add(label6);
		c.add(t2);
		c.add(new JLabel("                      "));
		c.add(label9);
		c.add(t4);
		c.add(new JLabel("   "));
		c.add(new JLabel("       "));
		c.add(new JLabel("                                         "));
		c.add(label11);
		c.add(t6);
		c.add(new JLabel("               "));
		c.add(label5);c.add(c1);c.add(c2);c.add(c3);c.add(c4);
		c.add(new JLabel("    "));
		c.add(label12);
		c.add(t9);
		c.add(new JLabel("                                       "));
		c.add(label13);
		c.add(t10);
		c.add(new JLabel("                        "));
		c.add(ta1);
		c.add(new JLabel("     "));
		c.add(ta2);
		c.add(new JLabel("                          "));
		c.add(button1);
		c.add(new JLabel(""));
        c.add(button2);
		c.add(new JLabel("         "));
		c.add(button3);
		c.add(new JLabel(""));
		c.add(button4);
		setVisible(true);
		button1.addActionListener(this);
		button2.addActionListener(this);
		button3.addActionListener(this);
		button4.addActionListener(this);
		setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
	}
  ## 2，写入
  if(e.getSource()==button3) {
			ta2.append("教师姓名："+t3.getText()+"\n"+
			"课程："+t4.getText()+"\n"+"上课地点："+t6.getText()
			+"\n"+"\n"+"编号："+t9.getText()
			+"\n"+"学分："+t10.getText()+"\n");
			StringBuffer t=new StringBuffer("教师姓名："+t3.getText()+"\n"+
					"课程："+t4.getText()+"\n"+"上课地点："+t6.getText()
					+"\n"+"\n"+"编号："+t9.getText()
					+"\n"+"学分："+t10.getText());
			try {
				FileWriter fw=new FileWriter("D:\\java1\\class.txt");
				fw.write(t.toString());
				fw.close();
				} 
			catch (IOException n) 
				{
				n.printStackTrace();
				}
# 六、程序运行截图
![image](https://github.com/849351726/4444/blob/master/jietu.png)
# 七，心得体会
通过这次学习GUI的编写，将之前的实验内容联系起来，深入了解监听器的用法以及容器的作用和各个组件之间是如何运用的。学会对文件的处理进行写入读取等。熟练使用GitHub以及使用gui编程的排版。深刻强化了自己对gui的了解以及写入读取文件。各个编程语言都是庞大的，只靠课上的那些是远远不够的还需要自己在网上不断地学习以及深化。通过本学期对JAVA语言的学习，使我对计算机语言有了更深入的理解与体会，知道了JAVA语言与其他语言的区别和特性，JAVA语言的学习过程可谓“痛并快乐着”。
		
