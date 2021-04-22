﻿

# **Power BI Desktop でのデータのモデル化、パート 1**

**このラボの推定所要時間: 45 分**

このラボでは、データ モデルの開発を開始します。テーブル間のリレーションシップを作成してから、データ モデルのわかりやすさと使いやすさを向上させるために、テーブルと列のプロパティを構成します。また、階層を作成し、クイック メジャーを作成します。

このラボでは次の作業を行う方法について説明します。

- モデル リレーションシップを作成する

- テーブルと列のプロパティを構成する

- 階層を作成する

- クイック メジャーを作成する

### **ラボ ストーリー**

このラボは、データの準備からレポートやダッシュボードとしての発行までの完全なストーリーとして設計された一連のラボのうちの 1 つです。ラボは任意の順序で完了できます。ただし、複数のラボを行う場合は、最初の 10 のラボを次の順序で行うことをお勧めします。

1. Power BI Desktop でのデータの準備

2. Power BI Desktop へのデータの読み込み

3. **Power BI Desktop でのデータのモデル化、パート 1**

4. Power BI Desktop でのデータのモデル化、パート 2

5. Power BI Desktop での DAX 計算の作成、パート 1

6. Power BI Desktop での DAX 計算の作成、パート 2

7. Power BI Desktop でのレポートの設計、パート 1

8. Power BI Desktop でのレポートの設計、パート 2

9. Power BI ダッシュボードの作成

10. Power BI Desktop におけるデータ分析の実施

11. Power BI でのページ分割されたレポートの作成

## **演習 1: モデルのリレーションシップを作成する**

この演習では、モデルのリレーションシップを作成します。

### **タスク 1: はじめに**

このタスクではこのラボ用の環境を設定します。

*重要: 前のラボから継続している (およびそのラボを完了している) 場合は、このタスクを完了しないで、次のタスクから続けてください。*

1. Power BI Desktop を開くには、タスク バーにある Microsoft Power BI Desktop のショートカットをクリックします。

	![画像 12](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image1.png)

2. 「はじめに」ウィンドウを閉じるには、ウィンドウの左上にある「**X**」をクリックします。

	![画像 11](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image2.png)

3. スターター Power BI Desktop ファイルを開くには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

4. 「**レポートを開く**」を選択します。

	![画像 10](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image3.png)

5. 「**レポートを参照**」をクリックします。

	![画像 8](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image4.png)

6. 「**開く**」ウィンドウで、**D:\DA100\Labs\configure-data-model-in-power-bi-desktop\Starter** フォルダーに移動します。

7. **Sales Analysis** ファイルを選択します。

8. 「**開く**」をクリックします。

	![画像 7](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image5.png)

9. 開いている情報ウィンドウをすべて閉じます。

10. ファイルのコピーを作成するには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

11. 「**名前を付けて保存**」を選択します。

	![画像 5](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image6.png)

12. 変更を適用するかどうかを確認するメッセージが表示されたら、「**適用**」をクリックします。

	![画像 15](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image7.png)

13. 「**名前を付けて保存**」ウィンドウで、**D:\DA100\MySolution** フォルダーに移動します。

14. **保存** をクリックします。

	![画像 3](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image8.png)

### **タスク 2: モデル リレーションシップを作成する**

このタスクでは、モデルのリレーションシップを作成します。

1. Power BI Desktop の左側で、「**モデル**」ビュー アイコンをクリックします。

	![画像 1](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image9.png)

2. 7 つのテーブルがすべて表示されていない場合は、水平方向に右へスクロールし、テーブルをドラッグして、すべてを同時に表示できるように、より近づけて配置します。

	*ヒント: ウィンドウの下部にあるズーム コントロールを使用することもできます。*

	*モデル ビューでは、各テーブルとリレーションシップ (テーブル間のコネクタ) を表示できます。**Power BI Desktop でのデータの準備**ラボでデータ読み込みのデータの準備リレーションシップ オプションを無効にしたため、現在、リレーションシップはありません。*

3. レポート ビューに戻るには、左側の「**レポート**」ビュー アイコンをクリックします。

	![画像 327](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image10.png)

4. すべてのテーブル フィールドを表示するには、「**フィールド**」ウィンドウで空の領域を右クリックし、「**すべて展開**」を選択します。

	![画像 328](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image11.png)

5. テーブルのビジュアルを作成するには、「**フィールド**」ウィンドウの **Product** テーブル内から、**Category** フィールドを確認します。

	![画像 329](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image12.png)

	*ラボでは、フィールドを参照するために省略表記を使用します。次のようになります: **Product | Category**。この例では、**Salesperson** はテーブル名、**Salesperson** はフィールド名です。*

6. テーブルに列を追加するには、「**フィールド**」ウィンドウで、**Sales | Sales** フィールドをオンにします。

7. テーブル ビジュアルに 4 つの製品カテゴリが一覧表示され、それぞれの Sales 値が同じで、Total も同じであることに注意してください。

	![画像 330](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image13.png)

	*問題は、テーブルが異なるテーブルのフィールドに基づいていることです。各製品カテゴリには、そのカテゴリの売上が表示されることが想定されています。ただし、これらのテーブル間にはモデルのリレーションシップがないため、**Sales** テーブルはフィルタリングされません。次に、テーブル間でフィルターを伝達するリレーションシップを追加します。*

8. 「**モデリング**」リボン タブの「**リレーションシップ**」グループ内から、「**リレーションシップの管理**」をクリックします。

	![画像 331](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image14.png)

9. 「**リレーションシップの管理**」ウィンドウで、まだ関係が定義されていないことに注意してください。

10. リレーションシップを作成するには、「**新規作成**」をクリックします。

	![画像 332](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image15.png)

11. 「**リレーションシップの作成**」ウィンドウの最初のドロップダウン リストで、**Product** テーブルを選択します。

	![画像 333](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image16.png)

12. 2 番目のドロップダウン リスト (**Product** テーブル グリッドの下) で、**Sales** テーブルを選択します。

	![画像 334](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image17.png)

13. 各テーブルの **ProductKey** 列が自動的に選択されていることに注意してください。

	*これらの列は同じ名前とデータ型を共有しているため、選択されました。*

14. 「**カーディナリティ**」ドロップダウン リストで、**一対多 (1:*)** が選択されていることに注意してください。

	*Power BI は、**Product**テーブルの **ProductKey** 列に一意の値が含まれていることを認識するため、カーディナリティが自動的に検出されました。一対多リレーションシップは最も一般的なカーディナリティで、このラボで作成するすべてのリレーションシップがこの種類になります。**Power BI Desktop でのデータのモデル化、パート 2** ラボでは多対多のカーディナリティに取り組みます。*

15. 「**クロス フィルターの方向**」ドロップダウン リストで、**単一** が選択されていることを確認します。

	*単一フィルター方向とは、フィルターが「片側」から「多側」に伝達することを意味します。この場合、**Product** テーブルに適用されたフィルターは **Sales** テーブルに伝達しますが、逆方向には伝達しません。**Power BI Desktop でのデータのモデル化、パート 2** ラボでは多対多のカーディナリティに取り組みます。*

16. 「**このリレーションシップをアクティブにする**」がオンになっていることを確認します。

	*アクティブなリレーションシップは、フィルターを伝達します。リレーションシップを非アクティブとしてマークして、フィルターが伝達しないようにすることができます。テーブル間に複数のリレーションシップ パスがある場合、非アクティブなリレーションシップが存在する可能性があります。この場合、モデル計算は特別な関数を使用してアクティブ化できます。**Power BI Desktop でのデータのモデル化、パート 2** ラボでは非アクティブなリレーションシップに取り組みます。*

17. 「**OK**」をクリックします。

	![画像 335](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image18.png)

18. 「**リレーションシップの管理**」ウィンドウで、新しいリレーションシップが表示されていることを確認し、「**閉じる**」をクリックします。

	![画像 336](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image19.png)

19. レポートでは、テーブル ビジュアルが更新され、製品カテゴリごとに異なる値が表示されていることを確認します。

	![画像 337](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image20.png)

	***Product** テーブルに適用されたフィルターは、**Sales** テーブルに伝達されるようになりました。*

20. モデル ビューに切り替えて、2 つのテーブルの間にコネクタがあることを確認します(テーブルが互いに隣接しているかどうかは問題になりません)。 

	![画像 338](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image21.png)

21. この図では、**1** および **「*」** インジケーターで表されるカーディナリティーを解釈できることに注意してください。

	*フィルターの方向は、矢印の向きによって表されます。実線はアクティブなリレーションシップを表し、破線は非アクティブなリレーションシップを表します。*

22. リレーションシップにカーソルを合わせると、関連する列が強調表示されます。

	*リレーションシップを作成する簡単な方法があります。モデル図では、列をドラッグ アンド ドロップして新しいリレーションシップを作成できます。*

23. 別の方法を使用して新しいリレーションシップを作成するには、**Reseller** テーブルから、**ResellerKey** 列を **Sales** テーブルの **ResellerKey** 列にドラッグします。

	![画像 339](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image22.png)

	*ヒント: 列をドラッグしたくない場合があります。このような状況が発生した場合は、別の列を選択し、もう一度ドラッグする列を選択して、もう一度やり直してください。図に新しいリレーションシップが追加されていることを確認します。*

24. 新しい方法を使用して、次の 2 つのモデル リレーションシップを作成します。

	- **Region | SalesTerritoryKey** から **Sales | SalesTerritoryKey**

	- **Salesperson | EmployeeKey** から **Sales | EmployeeKey**

	*このラボでは、**SalespersonRegion** および **Targets** テーブルは接続解除されたままです。営業担当者と地域の間には多対多のリレーションシップがあり、**Power BI Desktop でのデータのモデル化、パート 2** ラボでは、この高度なシナリオを使用して作業します。*

25. 図では、**Sales** テーブルが図の中央に配置され、関連するテーブルがその周りに配置されるようにテーブルを配置します。切断されたテーブルを横に配置します。

	![画像 340](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image23.png)

26. Power BI Desktop ファイルを保存します。

## **演習 2: テーブルを構成する**

この演習では、階層を作成し、列の非表示、書式設定、分類を行うことによって、各テーブルを構成します。

### **タスク 1: Product テーブルを構成する**

このタスクでは、**Product** テーブルを構成します。

1. モデル ビューの「**フィールド**」ウィンドウで、必要に応じて **Product** テーブルを展開してすべてのフィールドを表示します。

2. 階層を作成するには、「**フィールド**」ウィンドウで **カテゴリ** 列を右クリックし、「**階層の作成**」を選択します。

	![画像 341](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image24.png)

3. 「**プロパティ**」ウィンドウ (**フィールド** ウィンドウの左側) の「**名前**」ボックスで 、テキストを **Products** に置き換えます。

	![画像 344](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image25.png)

4. 階層に 2 つ目のレベルを追加するには、「**プロパティ**」ウィンドウの「**階層**」ドロップダウン リストで「**サブカテゴリ**」を選択します (ウィンドウ内で下にスクロールする必要がある場合があります)。

5. 3 番目のレベルを階層に追加するには、「**階層**」ドロップダウン リストで、**製品** を選択します。

6. 階層の設計を完了するには、「**レベル変更の適用**」をクリックします。

	![画像 343](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image26.png)

	*ヒント: **レベル変更の適用** をクリックすることを忘れないでください。この手順を見落とすことはよくある間違いです。*

7. 「**フィールド**」ウィンドウで、**製品** 階層に注目してください。

	![画像 347](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image27.png)

8. 階層レベルを表示するには、**製品** 階層を展開します。

	![画像 346](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image28.png)

9. 列を表示フォルダーに編成するには、「**フィールド**」ウィンドウで、まず **Background Color Format** 列を選択します。

10. **Ctrl** キーを押しながら、**Font Color Format** 列を選択します。

11. 「**プロパティ**」ウィンドウの「**表示フォルダ**」ボックスに、「**書式設定**」と入力します。

	![画像 348](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image29.png)

12. 「**フィールド**」ウィンドウで、2 つの列がフォルダー内にあることに注意してください。

	![画像 349](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image30.png)

	*表示フォルダーは、特に多数のフィールドで構成されるテーブルを生理するのに最適な方法です。*

### **タスク 2: Region テーブルを構成する**

このタスクでは、**Region** テーブルを構成します。

1. **Region** テーブルで、次の 3 つのレベルを持つ **地域** という名前の階層を作成します。

	- グループ

	- 国

	- 地域

	![画像 350](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image31.png)

2. **Country** 列 (**国** 階層レベルではない) を選択します。

3. 「**プロパティ**」ウィンドウで「**詳細**」セクション (ウィンドウの下部) を展開し、「**データ カテゴリ**」ドロップダウン リストから「**国/地域**」を選択します。

	![画像 352](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image32.png)

	*データ分類によってレポート デザイナーにヒントを提供できます。この場合、列を国または地域に分類すると、マップ ビジュアライゼーションをレンダリングするときに、Power BI はより正確な情報を得られます。*

### **タスク 3: Reseller テーブルを構成する**

このタスクでは、**Reseller** テーブルを構成します。

1. **Reseller** テーブルで、次の 2 つのレベルを持つ **リセラー** という名前の階層を作成します。

	- ビジネス タイプ

	- リセラー

	![画像 351](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image33.png)

2. **地理** という名前の 2 番目の階層を作成します。次の 4 つのレベルがあります。

	- 国-地域

	- 都道府県

	- 市

	- リセラー

	![画像 353](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image34.png)

3. 次の 3 つの列を分類します。

	- **Country-Region** を **国/地域** として

	- **State-Province** を **都道府県** として

	- **City** を **市** として

### **タスク 4: Sales テーブルを構成する**

このタスクでは、**Sales** テーブルを構成します。

1. **Sales** テーブルで、**Cost** 列を選択します

2. 「**プロパティ**」ウィンドウの「**説明**」ボックスに、次のように入力します。**標準原価に基づく**

	![画像 358](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image35.png)

	*説明は、テーブル、列、階層、またはメジャーに適用できます。「**フィールド**」ウィンドウでは、レポート作成者がフィールド上にカーソルを置くと、ヒントに説明テキストが表示されます。*

3. **Quantity** 列を選択します。

4. 「**プロパティ**」ウィンドウの「**書式設定**」セクション内から、「**桁区切り記号**」プロパティを「**オン**」にスライドします。

	![画像 357](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image36.png)

5. **Unit Price** 列を選択します。

6. 「**プロパティ**」ウィンドウの「**書式設定**」セクション内で、「**小数点以下桁数**」プロパティを **2** にスライドします。

7. 「**詳細**」グループ (下にスクロールして配置する必要がある場合があります) の「**集計の方法**「ドロップダウン リストで、「**平均**」を選択します。

	![画像 354](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image37.png)

	*既定では、数値列は値を合計して集計されます。この既定の動作は、レートを表す **Unit Price** のような列には適していません。既定の集計を平均に設定すると、有用な結果が得られます。*

### **タスク 5: プロパティを一括更新する**

このタスクでは、1 回の一括更新で複数の列を更新します。この方法を使用して列を非表示にし、列の値を書式設定します。

1. 「**フィールド**」ウィンドウで、**Product | ProductKey** 列を選択します。

2. **Ctrl** キーを押しながら、次の 13 列 (複数のテーブルにまたがる) を選択します。

	- Region | SalesTerritoryKey

	- Reseller | ResellerKey

	- Sales | EmployeeKey

	- Sales | ResellerKey

	- Sales | SalesOrderNumber

	- Sales | SalesTerritoryKey

	- Salesperson | EmployeeID

	- Salesperson | EmployeeKey

	- Salesperson | UPN

	- SalespersonRegion | EmployeeKey

	- SalespersonRegion | SalesTerritoryKey

	- Targets | EmployeeID

3. 「**プロパティ**」ウィンドウで、「**非表示**」プロパティを「**オン**」にスライドします。

	![画像 355](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image38.png)

	*列はリレーションシップによって使用されるか、行レベルのセキュリティ構成または計算ロジックで使用されるため、非表示に設定されました。*

	***Power BI Desktop でのデータのモデル化、パート 2** ラボでは、**UPN** 列を使用して行レベルのセキュリティを定義します。**Power BI Desktop での DAX 計算の作成、パート 1** ラボでは、**SalesOrderNumber** を計算に使用します。*

4. 次の 3 つの列を複数選択します。

	- Product | Standard Cost

	- Sales | Cost

	- Sales | Sales

5. 「**プロパティ**」ウィンドウの「**書式設定**セクション内から、「**小数点以下桁数**」プロパティを **0** (ゼロ) に設定します。

	![画像 356](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image39.png)

## **演習 3: モデル インターフェイスを確認する**

この演習では、レポート ビューに切り替えて、モデル インターフェイスを確認します。

### **タスク 1: モデル インターフェイスを確認する**

このタスクでは、レポート ビューに切り替えて、モデル インターフェイスを確認します。

1. レポート ビューに切り替えます。

2. 「**フィールド**」 ウィンドウで、次のことに注意してください。

	- 列、階層、およびそれらのレベルはフィールドであり、レポートのビジュアルを構成するために使用できます

	- レポート作成に関連するフィールドのみが表示されます

	- **SalespersonRegion** テーブルは表示されません。そのフィールドがすべて非表示になっているためです

	- **Region** および **Reseller** テーブルの空間フィールドは、空間アイコンが表示されています

	- シグマ記号 (Ʃ) が表示されたフィールドは、既定で集計されます

	- カーソルを **Sales | Cost** フィールドの上に置くと、ヒントが表示されます

3. **Sales | OrderDate** フィールドを展開すると、日付の階層が表示されます。

	![画像 359](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image40.png)

	***Targets | TargetMonth** フィールドも同様の階層を提供します。これらの階層は自分で作成したものではなく、自動的に作成されました。ただし、問題があります。Adventure Works の会計年度は、毎年 7 月 1 日に始まります。ただし、この自動的に作成された日付階層では、日付階層の年は毎年 1 月 1 日に始まります。*

	*この自動動作はオフにします。**Power BI Desktop での DAX 計算の作成、パート 1** ラボでは、DAX を使用して日付テーブルを作成し、Adventure Works 社のカレンダーを定義するように構成します。*

4. 自動時刻/日付時刻をオフにするには、「**ファイル**」リボン タブをクリックして、バックステージ ビューを開きます。

5. 左側の「**オプションと設定**」を選択し、「**オプション**」を選択します。

	![画像 360](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image41.png)

6. 左側にある「**オプション**」ウィンドウの「**現在のファイル**」グループで、「**データの読み込み**」を選択します。

	![画像 361](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image42.png)

7. 「**タイム インテリジェンス**」セクションで、「**自動の日付/時刻**」のチェックを外します。

	![画像 362](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image43.png)

8. 「**OK**」をクリックします。

	![画像 9](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image44.png)

9. 「**フィールド**」ウィンドウで、日付階層が使用できなくなっていることに注意してください。

	![画像 363](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image45.png)

## **演習 4: クイック メジャーを作成する**

この演習では、2 つのクイック メジャーを作成します。

### **タスク 1: クイック メジャーを作成する**

このタスクでは、利益と利益率を計算する 2 つのクイック メジャーを作成します。

1. 「**フィールド**」ウィンドウで、**Sales** テーブルを右クリックし、「**新しいクイック メジャー**」を選択します。

	![画像 366](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image46.png)

2. 「**クイック メジャー**」ウィンドウの「**計算**」ドロップダウン リストで、「**数値演算**」グループ内から「**減算**」を選択します。

	![画像 367](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image47.png)

3. 「**クイック メジャー**」ウィンドウの「**フィールド**」ウィンドウで、**Sales** テーブルを展開します。

4. **売上** フィールドを **基準値** ボックスにドラッグします。

5. **コスト** フィールドを **減算する値** ボックスにドラッグします。

	![画像 368](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image48.png)

6. 「**OK**」をクリックします。

	![画像 369](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image49.png)

	*クイック メジャーによって計算式が作成されます。シンプルで一般的な計算を簡単かつ迅速に作成できます。**Power BI Desktop での DAX 計算の作成、パート 2** ラボでは、このツールを使用せずにメジャーを作成します。*

7. 「**フィールド**」ウィンドウの **Sales** テーブル内で、新しいメジャーに注目します。

	![画像 370](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image50.png)

	*メジャーは、電卓アイコンが付いています。*

8. メジャーの名前を変更するには、メジャーを右クリックして、「**名前の変更**」を選択します。

	![画像 371](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image51.png)

	*ヒント: フィールドの名前を変更するには、フィールドをダブルクリックするか、フィールドを選択して **F2** を押します。*

9. メジャーの名前を **Profit** に変更し、**Enter** キーを押します。

10. **Sales** テーブルで、次の要件に基づいて 2 番目のクイック メジャーを追加します。

	- **除算** 数学演算を使用する

	- **分子** を **Sales | Profit** フィールドに設定する

	- **分母** を **Sales | Sales** フィールドに設定する

	- メジャーの名前を **Profit Margin** に変更する

	![画像 372](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image52.png)

	![画像 373](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image53.png)

11. **Profit Margin** メジャーが選択されていることを確認してから、「**メジャー ツール**」コンテキスト リボンで、フォーマットを小数点以下 2 桁の「**パーセンテージ**」に設定します。

	![画像 374](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image54.png)

12. 2 つのメジャーをテストするには、最初にレポート ページでテーブル ビジュアルを選択します。

13. 「**フィールド**」ウィンドウで、2 つのメジャーを確認します。

	![画像 375](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image55.png)

14. 右側のガイドをクリックしてドラッグし、テーブル ビジュアルを広げます。

	![画像 376](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image56.png)

15. メジャーが適切にフォーマットされた適切な結果を生成することを確認します。

	![画像 378](Linked_image_Files/03-configure-data-model-in-power-bi-desktop_image57.png)

### **タスク 2: 仕上げ**

このタスクではラボを完了します。

1. テーブルを削除するには、テーブルをクリックして (それをクリックして)、**Delete** キーを押します。

2. Power BI Desktop ファイルを保存します。

3. クエリを適用するかどうかを確認するメッセージが表示されたら、「**後で適用**」をクリックします。

4. 次のラボを開始する場合は、Power BI Desktop を開いたままにしておきます。

	***Power BI Desktop でのデータのモデル化、パート 2** ラボでは、多対多のリレーションシップと行レベルのセキュリティを構成することによって、データ モデルを拡張します。*