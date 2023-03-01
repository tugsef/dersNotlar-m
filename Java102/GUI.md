# GUI (Swing)

![image](https://user-images.githubusercontent.com/39422788/221799545-c3856079-a7a1-435e-bb3c-045757681ce7.png)

Swing mimarisi İki temel birleşen üzerene kurulur. Component ve Contenierlardır. Birleşenleri(Component) kullanmak için Conteiner(Konteynerlara) ihtiyaç duyarız.
- **JFRame** Ana kapsayıcı koyneyner 
- **JPanel**  JFrame liste , fotoğraf , buton eklemek isteyebiliriz bu amaçla JFrameleri Parçalara bölmek için **JPanel** kullanılır. JFarme içerisinde oluşturduğumuz bir 
bölmeye yarayan Conteiner lar denebilir.

```JAVA
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;

public class JFareandPanel {

	public  static void main(String[] args) {
		
		JFrame frame = new JFrame();
		frame.setSize(200,200); //Frame boyutu
		
		JButton button = new JButton("İlk Butonum");  //Button oluşturma
		
		
		JPanel panel = new JPanel();  // Panel oluşturma
		panel.add(button); // butonu panele ekleme
		
		frame.add(panel); //Paneli butona ekleme
		
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.setVisible(true); // gürünürlük
	}
	# **JOptionPane** çoğu programda karşılaştığımız hata aldığımızda evet hayırda karşımıza çıkar. statictir nesne üretmeye gerek kalmaz
	import javax.swing.JFrame;
import javax.swing.JOptionPane;

public class Test {

	public static void main(String[] args) {
		
		JFrame frame = new JFrame("JOptionalPane Kullanımı");
		
		JOptionPane.showMessageDialog(frame, "Dikkat" , "Hoşgeldin" , JOptionPane.WARNING_MESSAGE);
		JOptionPane.showInputDialog(frame , "Doğrulama Kodu Giriniz ...");
		
		String string = JOptionPane.showInputDialog(frame , "Evet Yazarak Onayla");
		System.out.println(string);
		
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

	
}
```
![image](https://user-images.githubusercontent.com/39422788/221816012-68bc7994-490c-4dbd-aee3-8c05354ca5d8.png)

- **JButton ve Butona Basma Olayı**
```JAVA
  import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;

public class JbuttonTest {
	public static void main(String[] args) {
		
		// setBounds(x , y , weight , high)
		
		
		JFrame frame = new JFrame("Button Kullanımı");
		
		
		JButton button = new JButton("Gönder");
		button.setBounds(150 , 150 , 100 , 50); //Button JFrame üzerinde nerde 
												// Konumlanacak
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				System.out.println("Butone Basıldı...");
				
			}
		});  // Butona basıldığında ne yapacak console Butona basıldı yazdırır.
		
		
		
		frame.add(button);
		frame.setSize(400,400);
		frame.setLayout(null);
		
		frame.setVisible(true);
		
		
	}
}
```
![image](https://user-images.githubusercontent.com/39422788/221825288-238cf960-1b3f-40f8-bf3f-488101f5f478.png)

- **JLabel** görüntülecek mesajların yazıldığı kısımdır. 
```JAVA
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;

public class Test {

	public static void main(String[] args) {
		//JLabel yazı
		//label.setBounds(x , y , weight , heigh)
		
		JFrame frame = new JFrame();
		frame.setTitle("JLabel Kullanımı");
		
		JLabel label = new JLabel("Burası JLabel Burada Yazılar Çıkar");
		label.setBounds(125 , 100 , 200 , 50);
		label.setEnabled(true);
		
		JButton button = new JButton();
		button.setBounds(150, 150 , 100 , 50);
		button.setText("Artır");
		
		button.addActionListener(new ActionListener() {
			int count = 1;
			
			
			@Override
			public void actionPerformed(ActionEvent e) {
				label.setText("Butona " + count++ + " kez tıklandı.");
				
			}
		});
	
		frame.add(button);
		frame.add(label);
		frame.setSize(400,400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}



```
![image](https://user-images.githubusercontent.com/39422788/221839127-3d2314dd-3c1a-44a0-908c-2af75d4a7339.png)    ![image](https://user-images.githubusercontent.com/39422788/221839236-7166fa10-284c-45ba-b4aa-966889e69da8.png)

- **JTextField** Yazı veya veri girebildiğimiz alanlara diyoruz

```JAVA
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JTextField;

public class Test {

	public static void main(String[] args) {
		// JTextField kullanıcıdav veri aldığımız kısım.
		// textField.bounds(x , y   , weight , heigh)
		// textField3.setEnabled(false);  Deger gıremezsın
		JFrame frame = new JFrame("JTextFieldOgrenıyorum");
		
		JTextField textField1 , textField2 , textField3;
		JLabel label1 , label2 , label3;
		
		label1 = new JLabel();
		label1.setText("Birinci Sayıyı Giriniz");
		label1.setBounds(115 , 50 , 150 , 30);
		
		textField1 = new JTextField();
		textField1.setBounds(115 , 85 , 150 , 30);
		
		label2 = new JLabel();
		label2.setText("İkinci Sayıyı Giriniz");
		label2.setBounds(115 , 110 , 150 , 30);
		
		textField2 = new JTextField();
		textField2.setBounds(115 , 140 , 150 , 30);
		
		label3 = new JLabel();
		label3.setText("Toplam");
		label3.setBounds(115 , 175 , 150 , 30);
		
		textField3 = new JTextField();
		textField3.setBounds(115 , 205 , 150 , 30 );
		textField3.setEnabled(false);  //deger giremezsin
		
		JButton button = new JButton();
		button.setText("Topla");
		button.setBounds(150 , 245 , 80 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				int number1 = Integer.parseInt(textField1.getText());
				int number2 = Integer.parseInt(textField2.getText());
				int total = number1 + number2;
				String info = String.valueOf(total);
				textField3.setText(info);
				
			}
		});
		
		frame.add(button);
		frame.add(label3);
		frame.add(textField3);
		frame.add(label2);
		frame.add(textField2);
		frame.add(label1);
		frame.add(textField1);
		frame.setSize(400,400);
		frame.setLayout(null);
		frame.setVisible(true);
	}

}

```

![image](https://user-images.githubusercontent.com/39422788/221851441-8d599264-a174-4ea5-9b27-0493d8513238.png)


- **JTextArea** Metinsel olarak yazmamızı sağlayan bir alandır örnek olrak yazılan metnin kelime sayısını ve harf sayısını bulalım
 ```JAVA
 import java.awt.Button;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JTextArea;

public class Test {
	public static void main(String[] args) {
		
		JFrame frame = new JFrame("JTextArea Kullanımı");
		
		JLabel label1;
		JLabel label2;
		JButton button;
		JTextArea area;
		
		label1 = new JLabel();
		label1.setBounds(75 , 25 , 100 , 30);
		
		
		label2 = new JLabel();
		label2.setBounds(225 , 25 , 100 , 30);
		
		
		area = new JTextArea();
		area.setBounds(75 , 65 , 250 , 150 );
		
		button = new JButton();
		button.setText("Onayla");
		button.setBounds(150 , 250 , 100 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				String text = area.getText();
				
				String words[] = text.split("\\s");
				
				label1.setText("Kelime Sayısı : " + words.length);
				label2.setText("Harf Sayısı : " + text.length());
				
				
			}
		});
		
		
		frame.add(button);
		frame.add(area);
		frame.add(label1);
		frame.add(label2);
		frame.setSize(400,400);
		frame.setLayout(null);
		frame.setVisible(true);
		
		
		
		
	}
}

 ```
![image](https://user-images.githubusercontent.com/39422788/221859985-c192fea5-0335-4cc3-b8d5-9f42dca060cd.png)


- **JPasswordField** şifre işlemleri için kullanılır text yazılırken güvenlik nedeni ile text simge nokta olarak gösterir
veriler char olarak yazılır.

```JAVA

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPasswordField;

public class Test {

	public static void main(String[] args) {
		//  JPasswordField
		
		JFrame frame = new JFrame("JPasswordField Kullanımı");
		
	   JLabel label;
	   JPasswordField passwordField;
	   JButton button;
	   
	   label = new JLabel();
	   label.setBounds(125 , 105 , 100 , 30 );
	   
		
		passwordField = new JPasswordField();
		passwordField.setBounds(125 , 145 , 150 , 30);
		
		button = new JButton();
		button.setText("Gönder");
		button.setBounds(162 , 185 , 75 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				String pasword = new String(passwordField.getPassword());
				label.setText(pasword);
				
			}
		});
		
		
		frame.add(button);
		frame.add(passwordField);
		frame.add(label);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

```
![image](https://user-images.githubusercontent.com/39422788/221867335-a2475171-024f-4031-8dfd-13a875278c2f.png)





- **JCheckBox** seçim kutusu
 
 
 ```JAVA
 import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JCheckBox;
import javax.swing.JFrame;

public class Test {

	public static void main(String[] args) {
		
		JFrame frame = new JFrame("JCheckBox Kullanımı");
		
		JCheckBox checkBox1 , checkBox2;
		
		checkBox1 = new JCheckBox("Evet");
		checkBox1.setBounds(100 , 100 , 150 , 30);
		
		checkBox2 = new JCheckBox("Hayır");
		checkBox2.setBounds(100, 140, 150, 30);
		
		JButton button = new JButton("Kontrol Et");
		button.setBounds(100 , 180 , 100 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				if(checkBox1.isSelected()) {
					System.out.println("Evet Seçildi.");
					
				}
				
				if(checkBox2.isSelected()) {
					System.out.println("Hayır Seçildi.");
				}
				
			}
		});
		
		
		
		frame.add(button);
		frame.add(checkBox2);
		frame.add(checkBox1);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

 ```

![image](https://user-images.githubusercontent.com/39422788/221879307-bec102ae-6ac4-4bea-87e5-d732ee443db1.png)


```JAVA
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;

import javax.swing.JButton;
import javax.swing.JCheckBox;
import javax.swing.JFrame;
import javax.swing.JLabel;

public class TestAddItemListener {

	public static void main(String[] args) {
		// addItemListener tıklandı mı tıklanmadı mı
		
		JFrame frame = new JFrame("JCheckBox Kullanımı");
		
		JCheckBox checkBox1 , checkBox2;
		JLabel label;
		
		checkBox1 = new JCheckBox("C++");
		checkBox1.setBounds(100 , 100 , 150 , 30);
		checkBox1.setName("C++");
		
		checkBox2 = new JCheckBox("Java");
		checkBox2.setBounds(100, 140, 150, 30);
		checkBox2.setName("Java");
		
		label = new JLabel("Seçim Yapınız ...");
		label.setBounds(75 , 65 , 150 , 30);
		
		checkBox1.addItemListener(new ItemListener() {
			
			@Override
			public void itemStateChanged(ItemEvent e) {
				label.setText(checkBox1.getName() + (e.getStateChange() == 1 ? "Seçildi" : "Seçilmedi") );
				
			}
		});
		
		checkBox2.addItemListener(new ItemListener() {
			
			@Override
			public void itemStateChanged(ItemEvent e) {
				label.setText(checkBox2.getName() + (e.getStateChange() == 1 ? "Seçildi" : "Seçilmedi"));
				
			}
		});
		
		frame.add(label);
		frame.add(checkBox1);
		frame.add(checkBox2);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

	}



```
![image](https://user-images.githubusercontent.com/39422788/221879682-03df68be-1fc9-4d6b-aa38-cd1d4996d3e6.png)        ![image](https://user-images.githubusercontent.com/39422788/221879866-b429192b-d7f4-49b6-8ce5-048be53485e7.png)

- **JRadioButton**
 ```JAVA
 import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.ButtonGroup;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JRadioButton;

public class Test {
	//buttonGroup.getSelection().getActionCommand() seçilenin bana kısa değerini getir.
	public static void main(String[] args) {
		
		JFrame frame = new JFrame();
		JRadioButton radioButton1 , radioButton2 , radioButton3;
		JButton button;
		ButtonGroup buttonGroup; //RadioButtonlar gruplanması gerekir yosa hepsi seçilebilir olur.
		
		radioButton1 = new JRadioButton("Kadın");
		radioButton1.setBounds(100 , 100 , 100 , 30 );
		radioButton1.setActionCommand("K");
		
		
		radioButton2 = new JRadioButton("Erkek");
		radioButton2.setBounds(100 , 135 , 100 , 30);
		radioButton2.setActionCommand("E");
		
		radioButton3 = new JRadioButton("İstemiyorum" , true); // ikinci parametre true seçili getirir.
		radioButton3.setBounds(100 , 170 , 100 , 30);
		radioButton3.setActionCommand("N");
		
		buttonGroup = new ButtonGroup();
		buttonGroup.add(radioButton1);
		buttonGroup.add(radioButton2);
		buttonGroup.add(radioButton3);
		
		button = new JButton("Gönder");
		button.setBounds(100 , 205 , 100 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				System.out.println(buttonGroup.getSelection().getActionCommand());
				
			}
		});
		
		
		frame.add(button);
		frame.add(radioButton3);
		frame.add(radioButton1);
		frame.add(radioButton2);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

 ```


![image](https://user-images.githubusercontent.com/39422788/221901859-3769f882-0d0e-4ae3-85a2-00b657b6deb6.png)


- **JComboBox***
```JAVA
import java.awt.Frame;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JButton;
import javax.swing.JComboBox;
import javax.swing.JFrame;

public class Test {

	public static void main(String[] args) {
		
		JComboBox<String> comboBox;
		JButton button;
		
		String arr[] = {"C" , "C++" , "Java" , "Go" };
		
		JFrame frame = new JFrame("JCombobox Kullanımı");
		
		comboBox = new JComboBox<>(arr);
		comboBox.setBounds(100 , 100 , 100 , 30);
		
		button = new JButton("Gönder");
		button.setBounds(100 , 150 , 100 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				System.out.println("Seçili Dil : " + comboBox.getSelectedItem());
				System.out.println("Seçili Dil : " + comboBox.getItemAt(comboBox.getSelectedIndex()));
				
			}
		});
		
		
		frame.add(button);
		frame.add(comboBox);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);
	}

}

```
![image](https://user-images.githubusercontent.com/39422788/221961098-825cde4d-4d83-48ea-b678-2fcc97668bd2.png)



- **JTable**
```JAVA
import javax.swing.JFrame;
import javax.swing.JScrollPane;
import javax.swing.JTable;

public class Test {

	public static void main(String[] args) {	
		JTable table;
		JScrollPane scrollpane;
		
		String[][] data = {{"1" , "FEN" , "85"} , {"2" , "MAT" , "95"}};
		String[] column = {"ID" , "DERS" , "NOTE"};
		
		
		JFrame frame = new JFrame("JTable Kullanımı");
		
		table = new JTable(data , column);
		table.setBounds(50 , 50 , 300 , 100);
		
		scrollpane = new JScrollPane(table);
		
		
	
		frame.add(scrollpane);
		frame.setSize(400 , 400);
		frame.setVisible(true);
	}

}

```

![image](https://user-images.githubusercontent.com/39422788/221967493-7cfdd1b0-dd06-40f7-add5-2aabda7019b4.png)

- **JLİST** iki farklı Jlist oluşturulmuş list1 de sadece tek seçim kodlanmış , list2 de bütün seçenekleri seçme ihtimali kodlanmıştır.
```JAVA
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.DefaultListModel;
import javax.swing.DefaultListSelectionModel;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JList;

public class Test {

	public static void main(String[] args) {
		DefaultListModel<String> dListModel1;
		DefaultListModel<String> dListModel2;
		JButton  button;
		JList<String> list1;
		JList<String> list2;
		
		JFrame frame = new JFrame("JList");
		
		dListModel1 = new DefaultListModel<>();
		dListModel1.addElement("Java");
		dListModel1.addElement("C++");
		dListModel1.addElement("PHP");
		dListModel1.addElement("Go");
		
		list1 = new JList<>(dListModel1);
		list1.setBounds(50 , 50 , 100 , 100);
		list1.setSelectionMode(DefaultListSelectionModel.SINGLE_SELECTION); // Sadece bir seçenek eklemek için
		
		dListModel2 = new DefaultListModel<>();
		dListModel2.addElement("BootStrap");
		dListModel2.addElement("Swing");
		dListModel2.addElement("Spring");
		dListModel2.addElement("VueJs");
		
		list2 = new JList<String>(dListModel2);
		list2.setBounds(50 , 200 , 100 , 100);
		
		button = new JButton("Gönder");
		button.setBounds(155 , 158 , 100 , 30);
		button.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				String txt = "";
				if(list1.getSelectedIndex() != -1) { // Seçili ise
					txt = "Seçili Dil " + list1.getSelectedValue() + "--->";
				}
				
				if(list2.getSelectedIndex() != -1) {
					txt += " Alt Teknoloji : " ;
					
					for (Object object : list2.getSelectedValuesList()) { //Çoklu seçimde list dönecektir
						txt += object + " " ;
					}
					
				}
				
				
				System.out.println(txt);
			}
		});
		
		frame.add(button);
		frame.add(list2);
		frame.add(list1);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);
		

	}

}

```
![image](https://user-images.githubusercontent.com/39422788/221979471-091a9187-c9fa-4703-b2d2-eabf3bba42e9.png)


- **JOptionPane** messaj diyololsrı , veri alma diyoloğu vb. statictir.
```JAVA
import javax.swing.JFrame;
import javax.swing.JOptionPane;

public class Test {

	public static void main(String[] args) {
		
		JFrame frame = new JFrame("JOptionalPane Kullanımı");
		
		JOptionPane.showMessageDialog(frame, "Dikkat" , "Hoşgeldin" , JOptionPane.WARNING_MESSAGE);
		
		
		String string = JOptionPane.showInputDialog(frame , "Doğrulama Kodu Giriniz ..."); // değere atanabilir.a
		System.out.println(string);
		
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}


```
![image](https://user-images.githubusercontent.com/39422788/222056405-3a759ac5-8cf6-456f-9b97-26af64f653fb.png)   ![image](https://user-images.githubusercontent.com/39422788/222056704-952e714e-5a5e-4042-9a07-2871f2829b02.png)


- **JScrollBar**
```JAVA
import java.awt.event.AdjustmentEvent;
import java.awt.event.AdjustmentListener;

import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JScrollBar;

public class Test {

	public static void main(String[] args) {
		//JScroollBar
		//scrollBar = new JScrollBar(ytaydikey , başlamakordinst , maaxsınırlama , min değeri  , maxdeğeri);
		
		JScrollBar scrollBar;
		JFrame frame;
		JLabel label;
		
		frame = new JFrame("JScrollBsr Kullanımı");
		
		label = new JLabel("Hoşgeldiniz...");
		label.setBounds(50 , 50 , 150 , 30);
		
		scrollBar = new JScrollBar(JScrollBar.VERTICAL , 50 , 10 , 10  , 150);
		scrollBar.setBounds(50, 100, 50, 100);
		scrollBar.addAdjustmentListener(new AdjustmentListener() {
			
			@Override
			public void adjustmentValueChanged(AdjustmentEvent e) {
				label.setText("ScollBar değeri : " + scrollBar.getValue());
				
			}
		});
		
		frame.add(label);
		frame.add(scrollBar);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);
		

	}

}

```

![image](https://user-images.githubusercontent.com/39422788/222060694-9c26caaa-c7ae-43f1-a4fd-285519b2f932.png)
- **JMenu**

![image](https://user-images.githubusercontent.com/39422788/222110467-8cf6ab80-5478-41e4-ba91-72ed12af624b.png)

```JAVA

import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.JFrame;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JMenuItem;
import javax.swing.JOptionPane;

public class Test {

	public static void main(String[] args) {
		
		
		JMenuBar menuBar;
		JMenu menu;
		JMenu suJMenu;
		
		JMenuItem menuItem1;
		JMenuItem menuItem2;
		JMenuItem menuItem3;
		
		JMenuItem subMenuItem1;
		JMenuItem subMenuItem2;
	
		
		
		JFrame frame = new JFrame("JMenu Kullanımı");
		
		menuBar = new JMenuBar();
		
		menu = new JMenu("JMenu");
		menu.add(menuItem1 =new JMenuItem("JMenuItem1"));
		menu.add(menuItem2 = new JMenuItem("JMenuItem2"));
		menu.add(menuItem3 = new JMenuItem("JMenuItem3"));
		
		suJMenu = new JMenu("subMenu");
		suJMenu.add(subMenuItem1 = new JMenuItem( "subMenu1"));
		suJMenu.add(subMenuItem2 = new JMenuItem("subMenu2"));
		
		subMenuItem2.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				JOptionPane.showMessageDialog(frame, "SubMenu2 açıldı..");
				
			}
		});
		
		menu.add(suJMenu);
		menuBar.add(menu);
		frame.setJMenuBar(menuBar);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

```
![2023-03-01](https://user-images.githubusercontent.com/39422788/222111099-f81f2f42-b390-40fb-87e8-70fe55299bdd.png)  ![image](https://user-images.githubusercontent.com/39422788/222111367-cd9d45b1-3732-43b7-9564-624725717ca7.png)

- **JPopupMenu**
```JAVA
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.MouseAdapter;
import java.awt.event.MouseEvent;
import java.awt.event.MouseListener;

import javax.swing.JFrame;
import javax.swing.JMenuItem;
import javax.swing.JOptionPane;
import javax.swing.JPopupMenu;

public class Test {

	public static void main(String[] args) {
		JPopupMenu popupMenu;
		
		JMenuItem cut;
		JMenuItem copy;
		JMenuItem  paste;
		
		JFrame frame = new JFrame("JPopupMenu kullanımı");
		 popupMenu = new JPopupMenu();
		 popupMenu.add(cut = new JMenuItem("Kesme") );
		 popupMenu.add(copy = new JMenuItem("Kopyala"));
		 popupMenu.add(paste = new JMenuItem("Yapıştır"));
		
		frame.addMouseListener(new MouseAdapter() {

			@Override
			public void mouseClicked(MouseEvent e) {
				popupMenu.show(frame , e.getX() , e.getY()); //Kordinatlar önemli
				
			}
			
			
		});
		
		copy.addActionListener(new ActionListener() {
			
			@Override
			public void actionPerformed(ActionEvent e) {
				JOptionPane.showMessageDialog(frame, "Kopyalandı...");
				
			}
		});
		
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);
		
		
		
		
		
	}

}

```

![2023-03-01 (2)](https://user-images.githubusercontent.com/39422788/222116325-9eb732f5-1fb3-4cd9-b38d-9b037161f714.png)   ![image](https://user-images.githubusercontent.com/39422788/222116510-80dfda8b-cf13-482d-9e52-16861b60cff9.png)

- **JProgressBar**
```JAVA
![image](https://user-images.githubusercontent.com/39422788/222128042-b1c714b2-e437-419c-bad5-e0c49fe34fb4.png)
import java.awt.Frame;

import javax.swing.JFrame;
import javax.swing.JProgressBar;

public class Test {

	public static void main(String[] args) {
		JFrame frame = new JFrame("JProgressBar");
		
		JProgressBar progressBar = new JProgressBar(0 , 200); //başlangıç ve bitiş süresi
		progressBar.setBounds(100 , 100 , 200 , 50);
		progressBar.setValue(0);
		progressBar.setStringPainted(true); // daha güzel gösterir.
		
		
		frame.add(progressBar);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);
		
		int i= 0;
		while (i <= 2000) {
			progressBar.setValue(i);
			
			i+=20;
			try {
				Thread.sleep(150);
			} catch (InterruptedException e) {
				// TODO Auto-generated catch block
				e.printStackTrace();
			}
			
			
		}
	}

}

```
![image](https://user-images.githubusercontent.com/39422788/222122553-3b52ee0e-6ef9-40d5-b9e6-0a469d2abb0b.png)

- **JTabbedPane**
```JAVA
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTabbedPane;

public class Test {

	public static void main(String[] args) {
		
		JPanel panel1;
		JPanel panel2;
		JPanel panel3;
		JLabel label1;
		JLabel label2;
		JLabel label3;
		
		JTabbedPane tabbedPane;
		
		JFrame frame = new JFrame("JTabbedPane Kullanımı");
		
		label1 = new JLabel("İlk Panel");
		panel1 = new JPanel();
		panel1.add(label1);
		
		label2 = new JLabel("İkinci Panel");
		panel2 = new JPanel();
		panel2.add(label2);
		
		label3 = new JLabel("Üçüncü Panel");
		panel3 = new JPanel();
		panel3.add(label3);
		
		tabbedPane = new JTabbedPane();
		tabbedPane.setBounds(50 , 50 , 200 , 200);
		tabbedPane.add("Birinci" , panel1);
		tabbedPane.add("İkinci" , panel2);
		tabbedPane.add("Üçüncü" , panel3);
		
		frame.add(tabbedPane);
		frame.setSize(400 , 400);
		frame.setLayout(null);
		frame.setVisible(true);

	}

}

```
![image](https://user-images.githubusercontent.com/39422788/222139658-c6d16c2c-025e-4603-9bf2-3685678cf29b.png)

- **Layout** paneli 5 parçaya döner...
```JAVA
import java.awt.BorderLayout;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;

public class Test {

	public static void main(String[] args) {
	//Birleşenleri 5 ayırır.
		JButton button1;
		JButton button2;
		JButton button3;
		JButton button4;
		JButton button5;
		
		JPanel panel;
		JFrame frame;
		
		frame = new JFrame("Layout");
		
		panel = new JPanel(new BorderLayout());
		panel.add(button1 = new JButton("KUZEY") , BorderLayout.NORTH);
		panel.add(button2 = new JButton("Güney") , BorderLayout.SOUTH);
		panel.add(button3 = new JButton("DOĞU") , BorderLayout.EAST);
		panel.add(button4 = new JButton("BATI") , BorderLayout.WEST);
		panel.add(button5 = new JButton("MERKEZ") , BorderLayout.CENTER);
		
		frame.add(panel);
		frame.setSize(400 , 400);
		frame.setVisible(true);
		

	}

}

```
![image](https://user-images.githubusercontent.com/39422788/222140081-122c4123-281a-437d-b6f3-8466e4d5606c.png)

- **GridLayout** Webde de kullanılmakta responsive(mobil) yapılarda kullanılan bir yapı  grid(ızgara) istediğim gibi paneli böyer (3 , 2 ) bir yapı oluşturalum

```JAVA
import java.awt.BorderLayout;
import java.awt.GridLayout;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;

public class GridLayaut {

	public static void main(String[] args) {
		JButton button1;
		JButton button2;
		JButton button3;
		JButton button4;
		JButton button5;
		JButton button6;
		
		JPanel panel;
		JFrame frame;
		
		frame = new JFrame("Layout");
		
		panel = new JPanel();
		panel.setLayout(new GridLayout(3 , 2));
		panel.add(button1 = new JButton("B1"));
		panel.add(button2 = new JButton("B2") );
		panel.add(button3 = new JButton("B3") );
		panel.add(button4 = new JButton("B4")  );
		panel.add(button5 = new JButton("B5") );
		panel.add(button6 = new JButton("B6")); 
		
		
		frame.add(panel);
		frame.setSize(400 , 400);
		//frame.pack();
		frame.setVisible(true);

	}

	}



```
![image](https://user-images.githubusercontent.com/39422788/222142508-944697e9-1638-4a7b-838d-a3e0c6544bca.png)


- **flowLayout** aldığı birleşeni yanyana yazar paneli ortalar.soldan sağa yazar birleşenlerin büyüklüğü birleşenin aldığı öğe belirler

```JAVA
import java.awt.FlowLayout;
import java.awt.GridLayout;

import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;

public class flowLayout {

	public static void main(String[] args) {
		JButton button1;
		JButton button2;
		JButton button3;
		JButton button4;
		JButton button5;
		JButton button6;
		
		JPanel panel;
		JFrame frame;
		
		frame = new JFrame("Layout");
		
		panel = new JPanel();
		panel.setLayout(new FlowLayout());
		panel.add(button1 = new JButton("B1"));
		panel.add(button2 = new JButton("B2") );
		panel.add(button3 = new JButton("B3") );
		panel.add(button4 = new JButton("B4")  );
		panel.add(button5 = new JButton("B5") );
		panel.add(button6 = new JButton("B6")); 
		
		
		frame.add(panel);
		frame.setSize(400 , 400);
		//frame.pack();
		frame.setVisible(true);

	}

}


````

![image](https://user-images.githubusercontent.com/39422788/222144102-f672baf0-830f-41c1-8f19-eb791172cd9c.png)

