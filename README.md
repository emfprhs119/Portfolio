�Ϲμ�
================
email : emfprhs119@gmail.com  
github : https://github.com/emfprhs119

[Pcd_App](https://github.com/emfprhs119/Pcd_App)
=================
> Dec 4, 2017 ~ Dec 20, 2017

Description
----------------
���� ������ ���� ���� ���� �Է��̳� ���� �Է½� ���� �Բ� ���� �߽ɺ��� ����� ������ ������ �Ÿ��� ����Ͽ� �����ִ� ���ø����̼�.

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

[Ȩ������](https://github.com/emfprhs119/Homepage)
====================
> Dec 10, 2017 ~ Dec 15, 2017

Description
------------------
Spring Framework ���ظ� ���� Ȩ������ ����

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

[������](https://github.com/emfprhs119/estimate)
===================
> May 29, 2017 ~ Aug 4, 2017 //���� �Ⱓ�� ���� commit �Ⱓ���� ��ü

Description
--------------------
������ �ۼ� ���α׷� ����� ������ ���� �ۼ��� (�����+������)���� �ܰ��� �����ǰ� (�ܰ�*����)���� ���ް����� �����Ǿ� �հ�ݾױ��� �Ѵ��� �� �� �ֵ��� ���� ���α׷�.�ۼ�,���� �� �ҷ�����,pdf ���Ϸ� �������� ����.

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