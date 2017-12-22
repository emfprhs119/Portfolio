하민수
================
email : emfprhs119@gmail.com  
github : https://github.com/emfprhs119

[Pcd_App](https://github.com/emfprhs119/Pcd_App)
=================
Term
> Dec 4, 2017 ~ Dec 20, 2017

Tool
> Java, Eclipse, Android Sdk

Description
----------------
원의 지름과 나눌 점의 수를 입력이나 각도 입력시 원과 함께 원의 중심부터 수평과 수직에 평행한 거리를 계산하여 보여주는 어플리케이션.

Sample Code
----------------
<pre><code>
public void pcdCalc(double pcd, int num, boolean rotation) {
	centerX = (int) (originX * xRatio);
	centerY = (int) (originY * yRatio);
	this.num = num;
	this.pcd_rad = pcd / 2;
	pointArr = new Point[num];

	for (int i = 0; i < num; i++) {
		double heightf = Math.sin(2 * Math.PI / num * (i + (rotation ? 0.5f : 0)) + 3 * Math.PI / 2);
		double widthf = Math.cos(2 * Math.PI / num * (i + (rotation ? 0.5f : 0)) + 3 * Math.PI / 2);
		pointArr[i] = new Point(heightf, widthf);
	}
}
</code></pre>

Screenshot
-----------------
![pcd_app](https://github.com/emfprhs119/Pcd_App/blob/master/capture.png?raw=true)
- - -
[홈페이지](https://github.com/emfprhs119/Homepage)
====================
Term
> Dec 10, 2017 ~ Dec 15, 2017

Tool
> Java, STS, JSP, JSON, Spring Framework

Description
------------------
Spring Framework 이해를 위한 홈페이지 제작

Sample Code
----------------
<pre><code>
@RequestMapping(value = "/project", method = RequestMethod.GET)
public String project(Model model) {
	List<String> cssList;
	cssList=new ArrayList<String>();
	cssList.add("header.css");
	cssList.add("style.css");
	cssList.add("body/project.css");
	cssList.add("body/sidebar.css");

	model.addAttribute("title","project");
	model.addAttribute("cssList",cssList);
	model.addAttribute("headerhtml", readHtml("header/header.html"));

	List<Map<String, String>> devList=new ArrayList<Map<String, String>>();

	JSONObject obj = readJSON("json/project.json");
	JSONArray devs=(JSONArray) obj.get("projects");
	for(int i=0;i < devs.size();i++) {
		obj=(JSONObject) devs.get(i);
		devList.add(getMapFromJsonObject(obj));
	}
	model.addAt tribute("projectList", devList);
	return "project";
}
</code></pre>

Screenshot
-----------------
![homepage](https://github.com/emfprhs119/Homepage/blob/master/capture.png?raw=true)
- - -
[견적서](https://github.com/emfprhs119/estimate)
===================
Term
> May 29, 2017 ~ Aug 4, 2017 //제작 기간이 꼬여 commit 기간으로 대체

Tool
> Java, Eclipse, Swing Component

Description
--------------------
견적서 작성 프로그램 자재비 가공비 수량 작성시 (자재비+가공비)으로 단가가 결정되고 (단가*수량)으로 공급가액이 결정되어 합계금액까지 한눈에 볼 수 있도록 만든 프로그램.작성,저장 및 불러오기,pdf 파일로 내보내기 지원.

Sample Code
-----------------
<pre><code>
void leftPage() {
	if (viewManager.getProductView().getCurrPage() > 1){
		if (viewManager.getProductView().getCurrPage() == 2)
			viewManager.swapPanel("front");
		viewManager.getProductView().removeLastPage();
		viewManager.getProductView().setCurrPage(viewManager.getProductView().getCurrPage() - 1);		
	}
	refresh();
}
</code></pre>
Screenshot
-----------------
![estimate](https://github.com/emfprhs119/estimate/blob/master/capture.png?raw=true)
