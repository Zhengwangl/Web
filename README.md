# Web
my first web

login.html

<form action="login" method="post">
		<input type="text" name="username" placeholder="请输入登录名">
		<input type="password" name="password" placeholder="请输入密码">
		<input type="submit" value="登录">
</form>
  
  LoginServlet.java
  
  
  package web;

import java.io.IOException;
import javax.servlet.ServletException;
import javax.servlet.annotation.WebServlet;
import javax.servlet.http.HttpServlet;
import javax.servlet.http.HttpServletRequest;
import javax.servlet.http.HttpServletResponse;

/**
 * Servlet implementation class LoginInServlet
 */
@WebServlet("/login")
public class LoginInServlet extends HttpServlet {
	private static final long serialVersionUID = 1L;
       
    /**
     * @see HttpServlet#HttpServlet()
     */
    public LoginInServlet() {
        super();
        // TODO Auto-generated constructor stub
    }

	/**
	 * @see HttpServlet#doGet(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		response.getWriter().append("Served at: ").append(request.getContextPath());
	}

	/**
	 * @see HttpServlet#doPost(HttpServletRequest request, HttpServletResponse response)
	 */
	protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {
		// TODO Auto-generated method stub
		//doGet(request, response);
		//从请求对象中获取参数：用户名 密码
				String username = request.getParameter("username");
				String password = request.getParameter("password");
				//根据用户名 密码，访问数据库，进行验证
				if ("zyc".equals(username) && "zyc".equals(password)) {
					response.getWriter().append("Login success");
				} else {
					response.getWriter().append("Login error");
				}
	}

}
