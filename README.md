# Hibernate2
Hibernate基础2

1.session 缓存
／**
	@Before
	public void init(){
		System.out.println("init");
		Configuration configuration = new Configuration().configure();
		ServiceRegistry serviceRegistry = new 	ServiceRegistryBuilder().applySettings(configuration.getProperties()).buildServiceRegistry();
		sessionFactory = configuration.buildSessionFactory(serviceRegistry);
		session = sessionFactory.openSession();
		transaction = session.beginTransaction();
				}*/
	/**
	@After
	public void destory(){
		System.out.println("destory");
		transaction.commit();
		session.close();
		sessionFactory.close();
	}*/
	/**
	@Test
	public void test() {
		News news = (News) session.get(News.class, 1);
		System.out.println(news);
		News news2 = (News) session.get(News.class, 1);
		System.out.println(news2);}
		*/
	结论执行一次查询数据库代码。
	只要session没结束生命周期，且没有清理缓存，则存放在它缓存中的对象也不会结束生命周期。
	
2.对session缓存进行操作
1flush 强制使数据库
2reflesh
3clear
	
	
