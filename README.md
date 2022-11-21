# JDBC
package com.jspider.jdbc_3;

import java.io.FileNotFoundException;
import java.io.FileReader;
import java.io.IOException;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
import java.sql.SQLException;
import java.util.Properties;

public class Dyanaic_updateJdbc {
	private static Connection connection;
	private static PreparedStatement preparedStatement;
	private static int result;
	private static Properties  properties=new Properties();
	private static FileReader fileReader;
	private static String filePath="C:\\Users\\91787\\OneDrive\\Desktop"
			+"\\J2EE\\jdbc_3\\resource\\db_info.properties";
	private static String query;
	
	public static void main(String[] args) {
		
		try {
			fileReader=new FileReader(filePath);
			properties.load(fileReader);
			Class.forName(properties.getProperty("driverpath"));
			connection=DriverManager.getConnection(properties.getProperty("dburl"), properties);
			
			query="select * from student";
			
			
			             result=preparedStatement.executeUpdate(query);
			
			System.out.println(result);
			
		} catch (FileNotFoundException e) {
			e.printStackTrace();
		} catch (IOException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (ClassNotFoundException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		} catch (SQLException e) {
			// TODO Auto-generated catch block
			e.printStackTrace();
		}
	}
	
