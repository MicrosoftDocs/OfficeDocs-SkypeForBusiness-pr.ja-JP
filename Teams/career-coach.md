---
title: キャリア コーチの購入、構成、および有効化を行Microsoft Teams
author: cichur
ms.author: v-cichur
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: キャリア コーチを購入、構成、および有効にする方法については、Microsoft Teams。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9911f880ba817afff10acb2a347a5c8c776d059c
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130029"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>キャリア コーチの購入、構成、および有効化を行Microsoft Teams

キャリア コーチは LinkedIn Microsoft Teams教育アプリの一部で、高等教育学生がキャリアの旅をナビゲートする個別のガイダンスを提供します。 キャリア コーチは、学生がキャリア パスを発見し、現実世界のスキルを高め、ネットワークを 1 か所で構築するための統合されたキャリア ソリューションを教育機関に提供します。

キャリア コーチの [詳細については、 を参照してください](https://aka.ms/career-coach)。

> [!NOTE]
> 学生、教職員向けキャリア コーチの機能を有効にするには、このガイドのベスト プラクティスと役立つヒントを使用します。 クイック プランニング [ガイドに関する記事を参照](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) してください。

## <a name="review-the-requirements"></a>要件を確認する

教育機関でキャリア コーチを有効にするには、アプリを起動して実行するために必要な情報を確認します。

**技術要件**

  - Office 365テナントとAzure Active Directory

  - Microsoft Teams

  - LinkedIn アカウントの接続 (Azure Active Directory

**ライセンス**

  - 教員 

  - 学生

> [!NOTE]
> 構成を完了するには、キャリア コーチ教員ライセンスを IT 管理者に割り当てる必要があります。

**教育機関のデータとファイル**

  - コース カタログのデータ

  - 提供される研究分野

  - 教育機関の LinkedIn ページ

  - LinkedIn Learning キャンパス サブスクリプション (優先)

## <a name="purchase-the-career-coach-licenses"></a>キャリア コーチ のライセンスを購入する

キャリア コーチは、教育機関向けソリューション (EES)、クラウド サービス プロバイダー (CSP)、および Microsoft 365 管理センター (Web ダイレクト) を通じて、資格を持つ高等教育機関 (中国とロシアを除く) で世界中で利用できます。 アプリMicrosoft Teams、顧客は A3/A5 または Microsoft 365/A3/A5 Office 365 A1必要があります。

### <a name="assign-app-licenses-to-users"></a>ユーザーにアプリ ライセンスを割り当てる

詳細な手順については、「ユーザーにライセンスを割り当てる [」を参照してください](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="turn-on-linkedin-account-connections"></a>LinkedIn アカウント接続を有効にする

キャリア コーチ **では、** 教育機関のユーザーが自分のアカウントをキャリア コーチ内でMicrosoft 365 LinkedIn アカウントに接続する機能を持っている必要があります。

1. Azure AD [組織](https://aad.portal.azure.com/) のグローバル管理者であるアカウントを使用して、Azure ADにサインインします。

2. [ユーザー] **を選択します**。

3. [ユーザー] **ページで** 、[ユーザー設定] **を選択します**。

4. **[LinkedIn アカウント接続] で**、ユーザーが自分のアカウントを接続して、一部の Microsoft アプリ内の LinkedIn 接続にアクセスできます。 ユーザーが自分のアカウントの接続に同意するまで、データは共有できません。

   - 教育機関 **のすべてのユーザー** に対してサービスを有効にするには、[はい] を選択します。

   - 教育機関 **で選択した** ユーザーのグループにのみサービスを有効にするには、[選択したグループ] を選択します。

   - 教育機関 **のすべてのユーザー** からの同意を取り消す場合は、[いいえ] を選択します。

LinkedIn アカウント[接続をネットワークに統合する方法Azure Active Directory](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="configure-career-coach-in-the-teams-admin-center"></a>管理センターでキャリア コーチをTeamsする

管理センターの管理者設定Microsoft Teams、教育機関用のキャリア コーチを構成し、ユーザーに対して有効にできます。

## <a name="access-the-career-coach-app-settings"></a>キャリア コーチ アプリの設定にアクセスする

[アプリ[の管理] ページを](/microsoftteams/manage-apps)使用して、教育機関Teamsカタログのアプリのアプリを表示します。

1. 管理者センターに **サインインTeamsします**。

2. 左側のナビゲーションで、[アプリの管理] **Teamsを**  >  **選択します**。  

    > [!NOTE]
    > ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。

3. キャリア コーチを検索 **または参照します**。  

4. [**キャリア コーチ] を** 選択し、[キャリア コーチ **] を設定。**  

    ![[キャリア コーチ] アプリが選択され、次のオプションが表示設定表示されます。](media/app-settings.png)

### <a name="configure-the-career-coach-app-settings"></a>キャリア コーチ アプリの設定を構成する

キャリア コーチには、次の 5 つの構成カテゴリがあります。

- [ブランドと設定](#brand-and-preferences)

- [LinkedIn の構成](#linkedin-configuration)

- [コース カタログ](#course-catalog)

- [研究分野](#fields-of-study)

- [カスタマイズ](#customization)

> [!NOTE]
> 学生、教職員向けアプリを効果的に有効にするには、ブランドと設定、LinkedIn 構成、コース カタログ、および学習フィールドが必要です。 

#### <a name="brand-and-preferences"></a>ブランドと設定

ブランドと環境設定の設定ページで教育機関の名前、ロゴ、既定の言語を設定します。

![管理センターのキャリア コーチ のブランド化セクション](media/brand-preferences.png)

##### <a name="educational-institution-icon"></a>教育機関のアイコン

教育機関アイコンは、教育機関固有のコンテンツ、アプリ全体のコース カタログ リソース、ダッシュボードの実際のエクスペリエンス セクションで識別するために、キャリア コーチ全体で使用されます。 アイコンの形式は次の形式が最適です。

 - 透過的な PNG
 - 縦横比 1:1
 - 最大サイズは 64 ピクセル x 64 ピクセルです。

##### <a name="educational-institution-thumbnail"></a>教育機関のサムネイル

教育機関のアイコンは、特定の画像がコースで使用できない場合に、アプリ全体のコース カタログ リソースに使用されます。 アイコンの形式は次の形式が最適です。

- A PNG
- 縦横比 16:9
- 最大サイズは 360 ピクセル x 200 ピクセルです。

#### <a name="linkedin-configuration"></a>LinkedIn の構成

LinkedIn 構成は、キャリア コーチと LinkedIn の一般卒業生データを接続します。

> [!NOTE]
> LinkedIn ページ接続が確認されていないと、キャリア コーチを有効にすることはできません。

##### <a name="add-and-confirm-the-linkedin-page"></a>LinkedIn ページを追加して確認する

教育機関の LinkedIn ページを決定します。 LinkedIn で検索するか、キャリア サービスのスタッフ メンバーと接続して、使用する正しいページを決定して、LinkedIn ページを探します。  
  
1. 管理者センターに **サインインTeamsします**。

1. [アプリ **Teams**  >  **アプリの管理**  >  **] を選択して、キャリア コーチ**  >  **LinkedIn 接続を選択します**。

2. 教育機関の LinkedIn ページ URL を入力します。  

3. **[適用]** を選択します。

4. 確認 URL をコピーし、教育機関の LinkedIn ページ管理者 [LinkedIn ページ管理者ドキュメントと共有します](https://www.linkedin.com/help/linkedin/answer/4783/linkedin-page-admins-overview?lang=en)。 検証リンクの有効期限は 30 日後です。  

   ![キャリア コーチの linkedin 設定](media/linkedin.png)  

#### <a name="course-catalog"></a>コース カタログ

コース カタログは、教育機関が学生に提供するコースとクラスを表します。 これらのコースは、次の 2 つの領域でアプリ内で使用されます。

- コースは、学習リソースの一部として返されます。  

- コースとコースのメタデータ (説明など) は、学生がトランスクリプトをアップロードするときに自分のスキルを識別するのに役立ちます。  

コース カタログを作成するには、教育機関で教えられたすべてのコースの一覧をまとめ、CSV ファイルとしてアップロードします。 このアプリはコース カタログから描画され、トランスクリプトから学生のスキルを特定し、受講するコースを提案します。 

> [!NOTE]
> 学生[情報の保護については、「Teams](location-of-data-in-teams.md)[のデータ](security-compliance-overview.md)の場所」と「セキュリティとコンプライアンス」を参照してください。 

##### <a name="course-catalog-documents-formatting-and-schema"></a>コース カタログ ドキュメントの書式設定とスキーマ

ドキュメントは、最大サイズが 18 MB の CSV 形式である必要があります。 ドキュメントには、必須フィールドのコース タイトル、 **コース** **ID、コース** URL が **含まれている必要があります**。 推奨されるフィールドを含め、より良い検索結果とスキル識別を返して、学生のエクスペリエンスを向上します。

> [!NOTE]
> 開始するには、 [サンプル コース カタログドキュメント]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) から開始します。

##### <a name="sample-csv-file"></a>サンプル .CSV ファイル

```
courseId,title,sourceLink,description,language,format,thumbnailLink,thumbnailAltText,educationLevel,topics
"AA-501","Analytics Foundations","https://example.com/course-id","This course equips the student with the knowledge and skills needed to conduct and present large-scale studies based on advanced analytics.","en-us","In-person","https://via.placeholder.com/360x200","Undergraduate","Alt text for the thumbnail","analytics, data science, data analysis, linear regression"
```

次の表は、コース カタログに含める項目を示しています。


| 名前             | 状態      | 型   | 説明                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | 必須    | 文字列 | 通常、コース ID (通常はトランスクリプトで生成された値にマップされます)。 |
| タイトル            | 必須    | 文字列 | 通常、コースのタイトル。                                                      |
| sourceLink       | 必須    | URL    | コース ページへの Web サイトのリンク。                                               |
| 説明      | 推奨 | 文字列 | コースの概要テキスト。                                              |
| 言語         | 推奨 | 文字列 | コースの言語。 標準の言語コードを使用します。                           |
| 書式           | 推奨 | 文字列 | 教育のモード (オンライン、ビデオ、対人など)。                              |
| thumbnailLink    | 推奨 | URL    | コースイメージへのサムネイル リンク。                                            |
| thumbnailAltText | 推奨 | 文字列 | 画像のアクセシビリティ代替テキスト                                           |
| educationLevel   | 推奨 | 文字列 | 学習レベル(例) 学部/卒業。                                       |
| トピック           | 推奨 | 文字列 | コースが教えるスキルに関連付けられているトピックまたはタグ。          |

##### <a name="add-the-course-catalog"></a>コース カタログを追加する

1. 管理者センターに **サインインTeamsします**。

1. [アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し、[キャリア** &gt; **コーチ] 設定** &gt; **カタログを選択します**。  

2. アップロード CSV 形式のコースを作成します。

4. **[適用]** を選択します。

   ![キャリア コーチ アプリのコース カタログ セクション](media/course-catalog.png)

#### <a name="fields-of-study"></a>研究分野

研究分野は、関心のある主要な分野、学術的専攻、および学位と同義です。 これらのタイトルは、学生がアプリの使用を開始し、パーソナライズされたプロファイルの設定を開始するときに参照されます。

エンジニアリング、英語、ビジネスなど、学生が利用できるすべての学習フィールドを追加します。 フィールドの一覧を使用すると、学生は興味のある分野を発見し、自分のプロフィールにフォーカス領域を追加できます。

> [!NOTE]
> 最初に、スタディ [ドキュメントのサンプル フィールドから始](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) める。
##### <a name="add-the-fields-of-study"></a>調査のフィールドを追加する

1. 管理者センターに **サインインTeamsします**。
1. [アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し**、[キャリア &gt; **コーチ設定** &gt; **フィールド] を選択します**。  

2. アップロードのフィールドを CSV 形式で指定します。

3. **[適用]** を選択します。

#### <a name="customization"></a>カスタマイズ

キャリア コーチは、教育機関に固有のカスタマイズが可能です。 カスタマイズでは、ダッシュボードへのエクスペリエンスの追加がサポートされます。 ジョブ ボード、イベント、キャリア サービス オフィス、キャリア関連イベント、学生クラブ、および学生が実際のエクスペリエンスを得るのに役立つその他のリソースへのリンクを追加する必要があります。

##### <a name="add-customized-experiences"></a>カスタマイズされたエクスペリエンスを追加する

1. 管理者センターに **サインインTeamsします**。

1. [アプリ **Teams** &gt; **アプリの管理** &gt; **] を選択し、[キャリア コーチ]**  >  **設定** &gt; **カスタマイズします**。

2. 各 URL、タイトル、および簡単な説明を追加します。  
  
3. **[適用]** を選択します。

### <a name="enable-the-app"></a>アプリを有効にする

構成が完了したら、学生とライセンスを取得したユーザーがキャリア コーチにアクセスできるアプリを有効にしてください。  
  
> [!NOTE]
> 管理者ロールのアクセス許可がTeams必要です。

1. 管理者センターに **サインインTeamsします**。

1. [アプリ **のTeams** &gt; **アプリの管理キャリア コーチ]** &gt; **を選択します**。

2. [状態] トグルを [許可] **に移動します**。  

  > [!NOTE]
  > [許可] は、教育機関のユーザーがアプリを利用できるという意味です。 [ブロック] は、学生がアプリを利用できないという意味です。

#### <a name="pin-the-app"></a>アプリをピン留めする

キャリア コーチをピン留めすると、学生がアプリにアクセスしやすく表示されます。

1. 管理者センターに **サインインTeamsします**。

1. [アプリ **Teams** &gt; **ポリシー] を** &gt; *選択します*。 

2. [固定 **されたアプリ] で**、[アプリの **追加] を選択します**。

1. [キャリア コーチ] **を検索し**、[追加] を **選択します**。

1. アプリが表示される順序を選択し、[保存] を **選択します**。

   学生には、キャリア コーチが固定Microsoft Teams通知されます。  

## <a name="resources"></a>リソース

次のリソースは、キャリア コーチ アプリの計画に役立ちます。

- [Microsoft Teams にようこそ](Teams-overview.md)

- [Teams の展開方法](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Microsoft Teams でのチームとチャネルの概要](teams-channels-overview.md)

- [管理センターでアプリMicrosoft Teams管理する](manage-apps.md)

- [セキュリティ、プライバシー、コンプライアンスに関するMicrosoft Teams](security-compliance-overview.md)

- [オンライン仮想向きキット](https://www.microsoft.com/education/remote-learning/virtual-orientation) 

- [チャネルの制限とTeams仕様](limits-specifications-teams.md)

- [Microsoft Teams のデータの場所](location-of-data-in-teams.md)

- [管理者向けトレーニングの開始Microsoft Teams](ITAdmin-readiness.md)

- [Teams のトラブルシューティング](/microsoftteams/troubleshoot/teams-welcome)

- [Microsoft Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
