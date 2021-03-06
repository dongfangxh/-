```
package MainPro;

import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import java.awt.event.WindowAdapter;
import java.awt.event.WindowEvent;

public class ShowMain extends Frame {
    MenuBar menuBar1;
    Menu menu1, menu2, menu3, menu4, menu5, menu6, menu7;
    MenuItem mi_book_add, mi_book_update, mi_book_delete, mi_reader_add,
    mi_reader_update, mi_reader_delete, mi_borrow, mi_back, mi_query_book,
    mi_query_reader, mi_update_pass, mi_exit;
    public void serRights(String rights){
        if (rights.equals("否")){
            //如果不是管理员，则禁止用户维护图书信息和读者信息
            //以及禁止进行借阅管理，即只能查询
            menu1.setEnabled(false);
            menu5.setEnabled(false);
        }
    }
    public ShowMain () {
        setTitle("图书管理系统");
        setLayout(new BorderLayout());
        setSize(640, 480);
        menuBar1 = new MenuBar();
        menu5 = new Menu("基础维护");//基础维护菜单
        menu5 = new Menu("图书维护");//图书维护菜单
        mi_book_add = new MenuItem("添加");//添加图书菜单
        mi_book_update = new MenuItem("修改");//修改图书菜单
        mi_book_delete = new MenuItem("删除");//删除图书菜单
        meun7 = new Menu("读者维护");//读者维护菜单
        mi_reader_add = new MenuItem("添加读者");
        mi_reader_update = new MenuItem("修改读者");
        mi_reader_delete = new MenuItem("删除读者");
        menu1 = new Menu("借阅管理");
        mi_borrow = new MenuItem("借书管理");
        mi_back = new MenuItem("还书管理");
        menu2 = new Menu("查询管理");
        mi_query_book = new MenuItem("图书查询");
        mi_query_reader = new MenuItem("读者查询");
        menu3 = new Menu("系统管理");
        mi_update_pass = new MenuItem("修改密码");
        mi_exit = new MenuItem("推出系统");
        //添加图书菜单
        mi_book_add.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_book_update.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_book_delete.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_reader_add.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_reader_update.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_reader_delete.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_borrow.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_back.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_query_book.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_query_reader.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_update_pass.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {

            }
        });
        mi_exit.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                DbOp.close();//关闭数据库
                System.exit(0);
            }
        });
        /*关闭窗口*/
        this.addWindowListener(new WindowAdapter() {
            @Override
            public void windowClosing(WindowEvent e) {
                super.windowClosing(e);
                DbOp.close();
                System.exit(0);
            }
        });
        menu5.add(menu6);
        menu6.add(mi_book_add);
        menu6.add(mi_book_update);
        menu6.add(mi_book_delete);
        menu5.add(menu7);
        menu7.add(mi_reader_add);
        menu7.add(mi_book_update);
        menu7.add(mi_book_delete);
        menu5.add(menu1);
        menu1.add(mi_borrow);
        menu1.add(mi_back);
        menu5.add(menu2);
        menu2.add(mi_query_book);
        menu2.add(mi_query_reader);
        menu5.add(menu3);
        menu3.add(mi_update_pass);
        menu3.add(mi_exit);
        menuBar1.add(menu5);
        menuBar1.add(menu1);
        menuBar1.add(menu2);
        menuBar1.add(menu3);
        setMenuBar(menuBar1);
        setLocationRelativeTo(null);//使窗体在屏幕上居中放置
        setVisible(true);//使窗体可见
    }
        //增加main()方法，主要为了调试程序界面
        public static void main (String[] args){
            new ShowMain();
        }
}
```