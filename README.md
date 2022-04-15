하민수
================
email : emfprhs119@gmail.com  
github : https://github.com/emfprhs119

[SpringCRUD](https://github.com/emfprhs119/SpringCRUD)
=================
Spring CRUD 구현 웹 서버

Infomation
----------------
Term : 2022.04 ~ 2022.04

Tool : __Spring Boot, JPA, MariaDB(Mysql), Thymeleaf, Springdoc(Swagger), IntelliJ__

Sample Code
----------------
```java
@RequestMapping("/")
@Controller
public class WebController {
    @Autowired
    MockService mockService;

    @GetMapping("/table")
    String table(Model model, @RequestParam(value="page", defaultValue="1") int page) {
        model.addAttribute("title","Database");
        model.addAttribute("appList",mockService.findAllPage(page-1,10));
        return "stable";
    }
	
	...
}
```

Screenshot
-----------------
![Screenshot_01.png](https://github.com/emfprhs119/SpringCRUD/blob/main/Screenshot/Screenshot_01.png?raw=true)
- - -

[DevTools](https://github.com/emfprhs119/DevTools)
=================
개발 보조도구 모음 앱

Infomation
----------------
Term : 2021.08 ~ 2021.09

Tool : __React, Javascript, Vscode__

Sample Code
----------------
```html
export default function Appbar(props) {
  const classes = useStyles();
  return (
    <Box className={classes.root}>
      <AppBar disableGutters={true} position="static" className={classes.appbar}>
        <Toolbar disableGutters={true}  variant="dense">
          <Typography variant="h5" className={classes.appname}>{props.currAppName}</Typography>
          {props.configHolders.map((configHolder,index)=>(
            <Fragment key={index}>
              <SelectMenu holder={configHolder} configs={props.configs} setConfigs={props.setConfigs}/>
              <AddDivider visible={(props.configHolders.length-1)!==index}/>
            </Fragment>
          ))}
        </Toolbar>
      </AppBar>
    </Box>
  );
}
```

Screenshot
-----------------
![Screenshot_01.png](https://github.com/emfprhs119/DevTools/blob/master/Screenshot/Screenshot_01.png?raw=true)
- - -

[DocV2](https://github.com/emfprhs119/DocV2)
=================
견적서, 거래명세서 작성 프로그램

Infomation
----------------
Term : 2021.10 ~ 2021.12

Tool : __C#, Sqlite, Visualstudio__

Sample Code
----------------
```csharp
private void InitConfig()
{
    string jsonString = File.ReadAllText(configFileName);
    int columnCount=0;
    using (JsonDocument document = JsonDocument.Parse(jsonString))
    {
        JsonElement docElement = document.RootElement;
        formName = docElement.GetProperty("Form").GetString();
        this.Text = formName;
        if (docElement.TryGetProperty("Orderer", out JsonElement OrdererElement))
            InitOrder(OrdererElement);
        if (docElement.TryGetProperty("Column", out JsonElement columnElements))
            sheetControl.InitSheetStyle(columnElements);
        columnCount = columnElements.GetArrayLength();
    }
    SQLiteWrapper.PrepareDB(columnCount);
}
```

Screenshot
-----------------
![Screenshot_01.png](https://github.com/emfprhs119/DocV2/blob/master/Screenshot/Screenshot_01.png?raw=true)
- - -

[Pcd_App](https://github.com/emfprhs119/Pcd_App)
=================
원의 중심부터 수평과 수직에 평행한 거리를 계산하여 보여주는 안드로이드 어플리케이션

Infomation
----------------
Term : 2017.12 ~ 2017.12

Tool : __Java, Eclipse, Android Sdk__

Sample Code
----------------
```java
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
```

Screenshot
-----------------
![pcd_app](https://github.com/emfprhs119/Pcd_App/blob/master/capture.png?raw=true)
- - -
[명세서](https://github.com/emfprhs119/specification)
====================
명세서 작성 프로그램  

Infomation
------------------
Term : 2017.12 ~ 2018.02

Tool : __Java, Eclipse, Swing, Sqlite__

Sample Code
----------------
```java
public boolean saveAll() {
	Demand demand;
	Specification specification;
	demand=demandView.getDemand();
	if (demand.getName() == null || demand.getName().trim().equals("")){
		JOptionPane.showMessageDialog(null, "demand not found error.");
		return false;
	}
	demand=demandView.saveCurrData();
	specification=specificationView.saveCurrData(demandView);
	productView.saveCurrData(specification.getIdQuery());
	frameLabel.setSpec(specification);
	return true;
}
```
Screenshot
-----------------
![specification](https://github.com/emfprhs119/specification/blob/master/capture.PNG?raw=true)
- - -
[견적서](https://github.com/emfprhs119/estimate)
===================
견적서 작성 프로그램  

Infomation
--------------------
Term : 2017.05 ~ 2017.08

Tool : __Java, Eclipse, Swing__

Sample Code
-----------------
```java
void leftPage() {
	if (viewManager.getProductView().getCurrPage() > 1){
		if (viewManager.getProductView().getCurrPage() == 2)
			viewManager.swapPanel("front");
		viewManager.getProductView().removeLastPage();
		viewManager.getProductView().setCurrPage(viewManager.getProductView().getCurrPage() - 1);		
	}
	refresh();
}
```
Screenshot
-----------------
![estimate](https://github.com/emfprhs119/estimate/blob/master/capture.png?raw=true)
