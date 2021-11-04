---
title: アプリの購入、構成、キャリア コーチ有効Microsoft Teams
author: cichur
ms.author: v-mahoffman
ms.reviewer: alaina.creager
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: アプリの購入、構成、有効化を行うキャリア コーチについてMicrosoft Teams。
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: f23f00249c23acb8397127bd51fd05206ce2f3f6
ms.sourcegitcommit: 6da1531dda6a0a3eecdca40e682783cc81c0d3e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60785090"
---
# <a name="purchase-configure-and-enable-career-coach-for-microsoft-teams"></a>アプリの購入、構成、キャリア コーチ有効Microsoft Teams

キャリア コーチは LinkedIn をMicrosoft Teams for Educationアプリです。このアプリは、高等教育の学生がキャリア体験をナビゲートするパーソナライズされたガイダンスを提供します。 キャリア コーチは、学生がキャリア パスを発見し、現実世界のスキルを高め、ネットワークを 1 か所で構築するための統一されたキャリア ソリューションを教育機関に提供します。

## <a name="supported-languages"></a>サポートされている言語

キャリア コーチは、次の言語でローカライズされます。

- 中国語 (簡体字、中国大陸)
- 中国語 (繁体字、台湾)
- 英語 (米国)
- 英語 (U.K.)
- フランス語 (カナダ)
- フランス語 (フランス)
- ドイツ語 (ドイツ)
- 日本語 (日本)
- ポルトガル語 (ブラジル)
- スペイン語 (スペイン)
- スペイン語 (メキシコ)

詳細[については、キャリア コーチ。](https://aka.ms/career-coach)

> [!TIP]
> このガイドのベスト プラクティスと役立つヒントを使用して、学生、教職員キャリア コーチの機能を有効にしてください。 クイック プランニング [ガイドに関する記事を参照](https://support.microsoft.com/office/c5d0b934-bfcf-4fe7-8a85-ba7bbb1b6ad4) してください。

## <a name="review-the-requirements"></a>要件を確認する

教育機関のキャリア コーチを有効にするには、アプリを起動して実行するために必要な情報を確認します。

**技術要件**

- Office 365を使用してテナントAzure Active Directory。

- Microsoft Teams。

- Azure Active Directory の LinkedIn アカウント接続。

**ライセンス**

- Faculty

- 学生

> [!IMPORTANT]
> 構成キャリア コーチ IT 管理者に、教職員のライセンスを割り当てる必要があります。

**教育機関からのデータとファイル**

- 教育機関のロゴと必要な形式のグラフィックアセット。

- コース カタログ データ。

- 提供される研究分野の一覧。

- 教育機関の [LinkedIn ページ](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

- 教育機関のプライバシー ポリシー URL。

- 教育機関は、キャリア サービスや学生の仕事の投稿など、キャリア関連のリソースにリンクしています (省略可能)。

- LinkedIn ラーニングのサブスクリプション (推奨)。

## <a name="purchase-the-career-coach-licenses"></a>ライセンスを購入キャリア コーチする

キャリア コーチ(中国とロシアを除く) は、教育機関向け登録ソリューション (EES)、クラウド サービス プロバイダー (CSP)、および Microsoft 365 管理センター (Web ダイレクト) を通じてアドオン ライセンスとして、資格のある教育機関向け (中国とロシアを除く) で利用できます。 アプリMicrosoft Teams、アドオン アプリを購入するには、Microsoft 365 A3/A5 または Office 365 A1/A3/A5 を持っているキャリア コーチがあります。

### <a name="assign-app-licenses-to-users"></a>ユーザーにアプリ ライセンスを割り当てる

詳細な手順については、「ユーザーにライセンスを割り当 [てる」を参照してください](/microsoft-365/admin/manage/assign-licenses-to-users)。

### <a name="turn-on-linkedin-account-connections"></a>LinkedIn アカウント接続を有効にする

キャリア コーチ、教育機関のユーザーは、Microsoft 365 アカウントを、キャリア コーチ 内で容易に利用できる LinkedIn アカウントに接続する機能を持っている必要があります。

1. 組織のグローバル[管理者](https://aad.portal.azure.com/)Azure ADアカウントを使用して、管理センターにAzure ADします。

2. [ユーザー] **を選択します**。

3. [ユーザー] **ページで** 、[ユーザー設定] **を選択します**。

4. **LinkedIn アカウント接続を適切** に構成するには、[はい] または [選択キャリア コーチ グループ] に設定する必要があります。

   ![組織内の LinkedIn アカウント接続を統合する](/azure/active-directory/enterprise-users/media/linkedin-integration/linkedin-integration.png)

   > [!NOTE]
   > ユーザーが自分のアカウントへの接続に同意するまで、データは共有しません。

   - 教育機関 **のすべてのユーザー** に対してサービスを有効にするには、[はい] を選択します。

   - [ **選択したグループ]** を選択して、教育機関で選択したユーザーのグループについてのみサービスを有効にしてください。

詳細については、 の[LinkedIn アカウント接続に関するページをAzure Active Directory。](/azure/active-directory/enterprise-users/linkedin-integration)

## <a name="access-the-career-coach-app-settings"></a>アプリの設定キャリア コーチアクセスする

管理Microsoft Teamsを使用して、教育機関キャリア コーチを構成し、ユーザーに対して有効にできます。

> [!IMPORTANT]
> ページにアクセスするには、グローバル管理者Teamsサービス管理者である必要があります。

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

2. 左側のナビゲーションで、[アプリの管理] **Teams アプリを**  >  **[選択します](https://admin.teams.microsoft.com/policies/manage-apps)**。  

3. を検索 **または参照** キャリア コーチ。  

4. [キャリア コーチ]**を** 選択し、[] を **選択設定。**  

    ![は、[キャリア コーチ] オプションが表示された状態で選択設定表示されます。](media/career-coach-app.png)

## <a name="configure-the-career-coach-app-settings"></a>アプリの設定キャリア コーチ構成する

キャリア コーチには、次の 5 つの構成カテゴリがあります。

- [ブランドと基本設定](#brand-and-preferences) - 必須

- [LinkedIn 接続](#linkedin-connection) - 必須

- [コース カタログ](#course-catalog) - 必須

- [研究分野](#fields-of-study) - 必須

- [カスタマイズ](#customization)

> [!IMPORTANT]
> 学生、教職員に対してアプリを効果的に有効にするには、ブランドと基本設定、LinkedIn の構成、コース カタログ、および研究分野が必要です。

### <a name="brand-and-preferences"></a>ブランドと基本設定

教育機関キャリア コーチブランドに合わせてカスタマイズします。 お客様は、著作権や商標の権利を含む他のユーザーの権利を尊重する責任を負います。

> [!IMPORTANT]
> これは必須のセクションです。キャリア コーチ設定を送信せずに有効にすることはできません。

![管理キャリア コーチの [ブランド] セクションに移動します。](media/career-coach-brand.png)

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

2. [アプリ **Teams**  >  **[アプリの管理] キャリア コーチ](https://admin.teams.microsoft.com/policies/manage-apps)**  >    >  **と基本設定] を選択します**。

3. アップロード **のアイコン をクリックします**。 このアイコンは、キャリア コーチ 全体で、教育機関に固有のコンテンツ、アプリ全体のコース カタログ リソース、ダッシュボードの実際のエクスペリエンス セクションで識別するために使用されます。 アイコンは、次の形式に最適です。

    - 透過的な PNG
    - 縦横比 1:1
    - 64 ピクセル x 64 ピクセルの最大サイズ

4. アップロード **のサムネイル をクリックします**。 サムネイルは、特定の画像がコースで使用できない場合に、アプリ全体のコース カタログ リソースに使用されます。 サムネイルの形式は次の形式が最適です。

    - A PNG
    - 縦横比 16:9
    - 360 ピクセル x 200 ピクセルの最大サイズ

5. 教育機関の **プライバシー ポリシー URL を追加します**。 追加した場合、教育機関のプライバシー ポリシーは、学生が新しいアプリでレビューキャリア コーチされます。

6. [送信] **を選択します**。

### <a name="linkedin-connection"></a>LinkedIn 接続

LinkedIn 構成は、LinkedIn キャリア コーチの一般の同窓生データと接続します。

> [!IMPORTANT]
> これは必須のセクションです。LinkedIn キャリア コーチ接続を確認しない場合、このセクションを有効にすることはできません。

#### <a name="add-the-linkedin-page"></a>LinkedIn ページを追加する
  
1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

2. [アプリ **Teams LinkedIn 接続**  >  **[でアプリ](https://admin.teams.microsoft.com/policies/manage-apps)**  >  **キャリア コーチ**  >  **管理する] を選択します**。

3. LinkedIn で検索し、[School] フィルターを選択して、[LinkedIn] ページ **を探** します。 または、キャリア サービスのスタッフ メンバーと接続して、使用する適切な LinkedIn 学校ページを決定します。 詳細については [、「LinkedIn ページを識別する方法」を参照してください](https://www.linkedin.com/help/linkedin/answer/40133/differences-between-a-linkedin-page-for-a-school-and-company?lang=en)。

    ![linkedin search for school.](media/career-coach-school-search.png)

4. LinkedIn 学校ページの URL を追加します。 URL は、会社のページではなく学校のページである必要があります。通常は として書式設定されます `https://www.linkedin.com/school/willow-university/` 。

   ![linkedin school ページの例。](media/career-coach-linkedin-page-url.png)

5. [送信] **を選択します**。
#### <a name="verify-the-linkedin-page"></a>LinkedIn ページを確認する 

> [!IMPORTANT]
> 確認は、教育機関の LinkedIn ページのスーパー管理者が完了する必要があります。

1. 正常に送信されると、ページが更新され、[確認] リンクと [確認]**リンク****の有効期限が表示されます**。 確認リンクは 30 日後に期限切れになります。

   ![キャリア コーチ アプリの linkedin 接続。](media/career-coach-linked-in.png)  

2. 確認リンクをコピーし、教育機関の LinkedIn ページのスーパー管理者と共有します。LinkedIn ページのスーパー管理者ロールの詳細については [、LinkedIn ページ管理者のドキュメントを参照してください](https://www.linkedin.com/help/linkedin/answer/102672)。

3. LinkedIn ページのスーパー管理者は、一意の確認リンクを使用して、キャリア コーチのページに関連付けることができます。 詳細については [、「LinkedIn ページの確認に関するその他の](https://www.linkedin.com/help/linkedin/answer/102672) ドキュメント」を参照してください。

   ![linkedin 開発者ポータルの linkedin ページ検証。](media/career-coach-linkedin-verification.png)

### <a name="course-catalog"></a>コース カタログ

コース カタログは、教育機関が学生に提供するコースとクラスを表します。

> [!IMPORTANT]
> これは必須のセクションです。キャリア コーチカタログなしでは有効にできません。

これらのコースは、アプリ内で次の 2 つの領域で使用されます。

- コースは学習リソースの一部として返されます。  

- コースとコースのメタデータ (説明など) は、学生がトランスクリプトをアップロードするときにスキルを識別するのに役立ちます。  

コース カタログを作成するには、教育機関で教えられたすべてのコースの一覧をまとめ、CSV ファイルとしてアップロードします。 アプリは、トランスクリプトから学生のスキルを識別し、受講するコースを提案するために、コース カタログから描画します。

#### <a name="add-the-course-catalog"></a>コース カタログを追加する

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

1. [アプリ **Teams** &gt; **[アプリの管理] キャリア コーチ設定](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  &gt;  &gt; **カタログ] を選択します**。  

2. アップロード、タイトル、sourceLink という必須の列を含む CSV 形式のコースを作成します。 各行には、必要な各列のデータを含める必要があります。 _推奨されるフィールドを含め、より良い検索結果とスキルの識別を返して、学生のエクスペリエンスを向上します。_

4. [送信] **を選択します**。

   ![キャリア コーチ アプリのコース カタログ セクション。](media/course-catalog.png)

#### <a name="course-catalog-document-format-and-schema"></a>コース カタログドキュメントの形式とスキーマ

ドキュメントは、最大サイズが 18 MB の CSV 形式である必要があります。 ドキュメントには、必須フィールドのコース **タイトル**、 **コース ID、** およびコース URL が **含まれている必要があります**。 

> [!TIP]
> 適切な書式設定 [を行うサンプル コース カタログ]( https://aka.ms/career-coach/docs/it-admins/sample-catalog) ドキュメントから始める。 _推奨されるフィールドを含め、より良い検索結果とスキルの識別を返して、学生のエクスペリエンスを向上します。_

次の表は、コース カタログに含める項目を示しています。

| 名前             | 状態      | 種類   | 説明                                                                    |
|------------------|-------------|--------|--------------------------------------------------------------------------------|
| courseId         | 必須    | string | 通常、コース ID (通常はトランスクリプトで生成される値にマップされます)。 |
| title            | 必須    | string | 通常、コースのタイトル。                                                      |
| sourceLink       | 必須    | URL    | コース ページへの Web サイト のリンク。                                               |
| description      | 推奨 | string | コースの概要テキスト。                                              |
| 言語         | 推奨 | string | コースの言語。 標準言語コードを使用します。                           |
| format           | 推奨 | string | 学習モード (オンライン、ビデオ、対人)。                                   |
| thumbnailLink    | 推奨 | URL    | コースの画像へのサムネイル リンク。                                            |
| thumbnailAltText | 推奨 | string | 画像のアクセシビリティ代替テキスト                                           |
| educationLevel   | 推奨 | string | 研究レベル (例: ) 学士/卒業者。                                       |
| topics           | 推奨 | string | コースが教えるスキルに関連付けられているトピックまたはタグ。          |

### <a name="fields-of-study"></a>研究分野

研究分野は、関心のある主な分野、学歴、および程度と同義です。 これらのタイトルは、学生がアプリの使用を開始し、パーソナライズされたプロファイルの設定を開始するときに参照されます。

> [!IMPORTANT]
> これは必須のセクションです。キャリア コーチフィールドの一覧がない場合は有効にできません。

#### <a name="add-the-fields-of-study"></a>研究分野を追加する

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。
1. [**アプリTeams** &gt; **[アプリの管理] キャリア コーチ設定](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;  &gt;  &gt; **フィールド] を選択します**。  

2. アップロード CSV 形式の研究分野を作成します。

3. [送信] **を選択します**。

#### <a name="fields-of-study-document-format-and-schema"></a>研究分野のドキュメント形式とスキーマ

エンジニアリング、英語、ビジネスなど、学生が利用できるすべての研究分野を追加します。 フィールドの一覧を使用すると、学生は興味のある研究分野を発見し、自分のプロファイルにフォーカス領域を追加できます。

> [!TIP]
> 適切な書式 [を確保するために、サンプル研究](https://aka.ms/career-coach/docs/it-admins/sample-fieldsofstudy) 分野のドキュメントから始める。

次の表は、研究分野に含める項目を示しています。

| 名前          | 状態   | 種類   | 説明                    |
|---------------|----------|--------|--------------------------------|
| fieldsOfStudy | 必須 | string | 研究分野の名前 |

### <a name="customization"></a>カスタマイズ

キャリア コーチは、教育機関に固有のカスタマイズが可能です。 カスタマイズでは、ダッシュボードへのエクスペリエンスの追加がサポートされます。 ジョブ ボード、イベント、キャリア サービス オフィス、キャリア関連のイベント、学生クラブ、学生が実際のエクスペリエンスを得るために役立つその他のリソースへのリンクを追加する方法をお勧めします。

#### <a name="add-customized-experiences"></a>カスタマイズされたエクスペリエンスを追加する

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

1. [アプリ **Teamsアプリ** &gt; **[の管理]](https://admin.teams.microsoft.com/policies/manage-apps)** &gt;   >  **キャリア コーチ設定** &gt; **を選択します**。

2. 各タイトル、URL、および簡単な説明を追加します。  
  
3. [送信] **を選択します**。

## <a name="making-career-coach-available-to-your-organization"></a>組織キャリア コーチを使用できる環境を作成する

これで、キャリア コーチ構成が行いました。 次の手順に従って、キャリア コーチ組織が使用Microsoft Teams。

### <a name="enable-the-app"></a>アプリを有効にする

構成が完了したら、学生とライセンスを取得したユーザーがアプリケーションにアクセスキャリア コーチ。  
  
> [!IMPORTANT]
> グローバルまたは管理者ロールのアクセスTeams必要があります。

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

1. [アプリ **Teamsアプリ** &gt; **[の管理] を](https://admin.teams.microsoft.com/policies/manage-apps)** &gt; **選択キャリア コーチ。**

2. [状態] トグルを [許可] **に移動します**。  

   > [!NOTE]
   > **許可とは** 、教育機関のユーザーがアプリを利用できるという意味です。 ブロックとは、アプリが学生が利用できないという意味です。

### <a name="add-career-coach-as-an-installed-app"></a>インストールキャリア コーチとしてアプリを追加する

> [!IMPORTANT]
> この手順により、組織キャリア コーチ適切に構成され、学生がユーザーを見キャリア コーチ。

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

2. [Teams **セットアップ ポリシー** &gt; **] を選択し**、優先するポリシーを選択します。
使用するポリシーが不明な場合は[、Microsoft Teams ポリシー](/microsoftteams/policy-packages-edu)管理に関するドキュメントを参照するか、教育ポリシー[](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings)ウィザードを使用して、Microsoft Teams のポリシーを構成します。

3. [インストール済みアプリ] で、[アプリの **追加] を選択します**。

4. [インストール済みアプリの追加] ウィンドウで、ユーザーがアプリを起動するときに自動的にインストールするアプリTeams。 アプリのアクセス許可ポリシーでアプリをフィルター処理することもできます。 アプリの一覧を選択したら、[追加] を **選択します**。

5. **[保存]** を選択します。

> [!NOTE]
> ポリシーを編集または割り当てると、変更が有効なまで数時間かかる場合があります。 変更キャリア コーチ完了するまで、Microsoft Teams アプリは使用できません。

### <a name="pin-the-app"></a>アプリをピン留めする

アプリをキャリア コーチすると、アプリのアクセスがしやすく、学生に表示されます。

1. 管理センター **[にTeamsします](https://admin.teams.microsoft.com)**。

2. [Teams **セットアップ ポリシー** &gt; **] を選択し**、優先するポリシーを選択します。
使用するポリシーが不明な場合は[、Microsoft Teams ポリシー](/microsoftteams/policy-packages-edu)管理に関するドキュメントを参照するか、教育ポリシー[](/microsoftteams/easy-policy-setup-edu?tabs=students%2Cstudent-settings)ウィザードを使用して、Microsoft Teams のポリシーを構成します。

3. [ピン **留めされたアプリ] で**、[アプリの **追加] を選択します**。

4. を検索 **キャリア コーチ** し、[追加] を **選択します**。

5. アプリを表示する順序を選択し、[保存] を **選択します**。

> [!NOTE]
> 学生には、ピン留めされたMicrosoft Teamsがキャリア コーチ通知されます。

詳細 [については、「Microsoft でアプリセットアップ ポリシーを管理](/microsoftteams/teams-app-setup-policies) する」を参照してください。


## <a name="troubleshooting"></a>トラブルシューティング

- キャリア コーチ アプリに "キャリア コーチ がすぐに使用するために設定されています" と表示される場合、必要なセクション __は完了していありません__。 次の __セクションは__、キャリア コーチ を使用するには、完了する必要 [があります。ブランド](#brand-and-preferences)と基本設定 [、LinkedIn 接続](#linkedin-connection)、コース [カタログ](#course-catalog)、および研究 [分野](#fields-of-study)。

- コース カタログと研究分野の CV には、必要な形式と最大サイズが 18 MB です。 適切な構成[キャリア コーチ、コース カタログ](#course-catalog-document-format-and-schema)ドキュメント スキーマとキャリア コーチ[の](#fields-of-study-document-format-and-schema)フィールドを参照してください。

- 必須フィールドを含む設定ページでは、フィールドが完了していない場合、ページは送信されません。 警告メッセージは表示されません。ページは単に送信されない。

- アプリケーションを初キャリア コーチ、"アプリの設定を更新できない" というエラー バナーが表示される場合があります。 もう一度やり直してください。" というエラーが これは、テナントがアプリケーション アプリをプロビジョニングキャリア コーチ、最大 15 分かかる場合があります。 この場合は、もう一度送信するまで 15 分待ちます。

- アプリがキャリア コーチに表示されない場合Microsoft Teamsポリシーの変更が有効になされていない可能性があります。 ポリシーの変更は、更新に数時間かかる場合があります。 変更キャリア コーチ完了するまで、Microsoft Teams アプリは使用できません。

## <a name="removing-your-tenant-data"></a>テナント データの削除

テナント データには、アプリケーション構成の一部としてアップロードまたは生成される情報が含まれます。 キャリア コーチ テナント内のすべてのデータを削除するには、テナントのグローバル管理者にサポート チケットを[](https://edusupport.microsoft.com/support?product_id=career_coach)開き、テナントのデータを完全に削除します。 このプロセスは元に戻すことができない点に注意してください。 データの削除が完了すると、キャリア コーチ アプリケーションは、すべてのユーザーに対して事前に構成された、カスタマイズされていない状態に戻り、Teams 管理者は、アプリケーションを引き続き使用するには、アプリケーションを再設定する必要があります。

削除のプロセスを次に示します。

- テナントのデータを完全に削除する要求を明確に示すサポート チケットをテナント グローバル管理者が送信する必要があります。 **削除のデータ セットまたはタイム** ウィンドウを制限する機能はありません。

- ファイルが送信された後、サポート チケットは、コンプライアンスの最小限の保持ポリシーを満たすために、1 週間後に対処されます。 この期間中に操作をキャンセルできます。

- 1 週間後、キャリア コーチチームは、テナントに関連するすべてのデータが削除されます。 Microsoft サポートはチケットを監視し、削除プロセスが完了した後 **、30** 日以内に通知します。


## <a name="resources"></a>リソース

次のリソースは、アプリの計画キャリア コーチ役立ちます。

- [Microsoft Teams にようこそ](Teams-overview.md)

- [Teams の展開方法](get-started-with-teams-resources-for-org-wide-rollout.md?tabs=SmallBusiness)

- [Microsoft Teams でのチームとチャネルの概要](teams-channels-overview.md)

- [Microsoft Teams 管理センターでのアプリの管理](manage-apps.md)

- [オンライン仮想向きキット](https://www.microsoft.com/education/remote-learning/virtual-orientation)

- [チャネルの制限Teams仕様](limits-specifications-teams.md)

- [管理者向けトレーニングのMicrosoft Teams](ITAdmin-readiness.md)

- [Teams のトラブルシューティング](/microsoftteams/troubleshoot/teams-welcome)

- [Microsoft Teams のアプリのアクセス許可ポリシーを管理する](teams-app-permission-policies.md)
