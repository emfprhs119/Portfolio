하민수
================
email : emfprhs119@gmail.com  
github : https://github.com/emfprhs119

[DevTools](https://github.com/emfprhs119/DevTools)
=================
Term
> 2021.08 ~ 2021.09

Tool
> React, Javascript, Vscode

Description
----------------
개발 보조도구 모음 앱

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
            <Fragment  key={index}>
          <SelectMenu 
              holder={configHolder}
              configs={props.configs} 
              setConfigs={props.setConfigs} />
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
Term
> 2021.10 ~ 2021.12

Tool
> C#, sqlite, Visualstudio

Description
----------------
견적서, 거래명세서 작성 프로그램

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
Term
> 2017.12 ~ 2017.12

Tool
> Java, Eclipse, Android Sdk

Description
----------------
원의 지름과 나눌 점의 수를 입력이나 각도 입력시 원과 함께 원의 중심부터 수평과 수직에 평행한 거리를 계산하여 보여주는 안드로이드 어플리케이션

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
Term
> 2017.12 ~ 2018.02

Tool
> Java, Eclipse, Swing, sqlite

Description
------------------
명세서 작성 프로그램  

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
Term
> 2017.05 ~ 2017.08

Tool
> Java, Eclipse, Swing

Description
--------------------
견적서 작성 프로그램  

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
