����ע�ⷽʽ���
ʵ��������ע�ⷽʽ���ٶ�ϵͳ������㣬����Ҫ������򷽷�����ע�⼴�ɣ���������Ӱ�죩
�����������:
1,web.xml������filter,url-pattern������Ҫ����restful�ӿ�,��ֹ��̬��Դ����
  <filter>
		<filter-name>cat-filter</filter-name>
		<filter-class>com.dianping.cat.servlet.CatFilter</filter-class>
	</filter>
	<filter-mapping>
		<filter-name>cat-filter</filter-name>
		<url-pattern>/test1/*</url-pattern>
		<url-pattern>/test2/*</url-pattern>
		<dispatcher>REQUEST</dispatcher>
		<dispatcher>FORWARD</dispatcher>
	</filter-mapping>
	
2,CatCacheTransactionע��ʾ��
		@CatCacheTransaction
    public V get(K key) {
        
    }
		@CatCacheTransaction
    public void put(K key, V value) {
       
    }
		@CatCacheTransaction
    public void delete(K key) {  
       
    }

3,CatHttpRequestTransactionע��ʾ��,URL�ۺ�ע��
		@RequestMapping(value = "/orders/{userId}/{orderStatus}")
    @ResponseBody
    @CatHttpRequestTransaction(type = "URL", name = "/orders")
    public String userOrders() {
    
    }
    
4,CatDubboClientTransactionע��ʾ��
		@CatDubboClientTransaction(callApp="orders",callServer = "orderServer")
    public List<Long> getOrdersByUser() {
        
    }