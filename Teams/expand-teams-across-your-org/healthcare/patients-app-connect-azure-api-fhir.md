---
title: 患者アプリを FHIR の Azure API に接続する
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: anach
description: Microsoft Teams の患者アプリを FHIR 用 Azure API (ファースト 医療相互運用性リソース) に接続する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 4e41b071ef1724043f45c3783b062108d29a5190
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731155"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>患者アプリを FHIR の Azure API に接続する

> [!NOTE]
> 2020 年 10 月 30 日から、患者アプリは廃止され、Teams の [リスト アプリに](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db) 置き換されました。 患者アプリのデータは、チームをバックアップする Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータは、このグループに保持されますが、ユーザー インターフェイスからアクセスできなくなりました。 ユーザーはリスト アプリを使用してリストを [再作成できます](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)。
>
>リストを使用すると、医療組織のケア チームは、ラウンドや学際的なチーム会議から一般的な患者監視まで、シナリオに関する患者リストを作成できます。 使用を開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「リスト アプリを管理する [」を参照してください](../../manage-lists-app.md)。

Microsoft Teams の患者アプリが FHIR インスタンスの Azure API にアクセスするには、次の手順に従います。 この記事では、テナントで [FHIR](https://azure.microsoft.com/services/azure-api-for-fhir/) インスタンスの Azure API がセットアップされ、構成されていることを前提とします。  テナントに FHIR インスタンスの Azure API をまだ作成していない場合は、「クイック スタート: Azure portal を使用して FHIR 用 Azure API を展開する」を [参照してください](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart)。

1. ここを [クリックして](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 、患者アプリに対する管理者の同意を付与します。 メッセージが表示されたら、テナント管理者またはグローバル管理者の資格情報を使用してサインインし、[承諾] をクリックして必要なアクセス許可を付与します。

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request.png)

    承諾した後、ウィンドウを閉じます。 次のようなページが表示されます。 ページ上のエラー メッセージは無視できます。 これは害を及ぼしません。同意が与えらたかどうかを示します。 (この URL のよりユーザー向けのページを作成中です。 お楽しみください)

    ![患者アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request-granted.png)

2. 管理者の資格情報 [で Azure Portal](https://portal.azure.com) にサインインします。

3. 左側のナビゲーションで **、[Azure Active Directory]** を選択し、[エンタープライズ アプリケーション **] を選択します**。

    患者 (開発 **)** という名前の行を探し、オブジェクト **ID** 列の値をクリップボードにコピーします。

    ![Azure Portal の患者 (開発) 行のスクリーンショット](../../media/patients-app-azure-portal-object-id.png)

4. (患者アプリを検索するか、リソースを参照して) 患者アプリを接続する FHIR リソース インスタンスの Azure API に移動し、そのインスタンスの設定を開きます。

    ![Azure portal の FHIR インスタンス設定の Azure API のスクリーンショット](../../media/patients-app-azure-portal-instance-settings.png)

5. [ **認証]** をクリックし、手順 3 でコピーしたオブジェクト ID を [許可されたオブジェクト ID] ボックスに **貼り付** けます。 これにより、患者アプリは FHIR サーバーにアクセスできます。 オブジェクト ID を貼り付けると、Azure Active Directory によって検証され、その横に緑色のチェック マークが表示されます。

    ![Azure portal の認証設定のスクリーンショット](../../media/patients-app-azure-portal-authentication.png)

6. **[保存]** をクリックします。 これにより、インスタンスが再配置されます。これには数分かかる場合があります。

7. [ **概要]** をクリックし、FHIR メタデータ エンドポイントから URL **をコピーします**。 メタデータ タグを削除して FHIR サーバー URL を取得します。 たとえば `https://test02-teamshealth.azurehealthcareapis.com/` 、.

    ![Azure Portal のメタデータ エンドポイント](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. Teams で、チームに読み込まれている患者アプリ インスタンスに移動し、[設定] をクリックし、[リンク] ボックスに FHIR サーバー エンドポイントの URL を入力します。 次に、[接続 **] を** クリックして接続を確立し、患者をリストに追加します。  

    ![ Teams の患者アプリの設定](../../media/patients-app-teams.png)

    この手順で Teams に接続するときにエラーが発生した場合は、エラーの詳細なスクリーンショット [、Fiddler](https://www.telerik.com/download/fiddler) からのログ、その他の再現手順をメールに送信し、件名行に "患者アプリ – EMR モードトラブルシューティング" を [teamsforhealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com)に送信します。

## <a name="related-topics"></a>関連項目

- [患者アプリの概要](patients-app-overview.md)
- [電子医療記録を Microsoft Teams に統合する](patients-app.md)
