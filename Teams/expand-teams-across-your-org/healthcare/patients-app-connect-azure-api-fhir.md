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
description: Azure API for FHIR (Fast Healthcare Interoperability Resources) Microsoft Teamsで Patients アプリを Azure API に接続する方法について説明します。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: e06e422765c1d1d633414d24dff48e2801067f15
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096269"
---
# <a name="connect-the-patients-app-to-azure-api-for-fhir"></a>患者アプリを FHIR の Azure API に接続する

> [!NOTE]
> 2020 年 10 月 30 日より、患者アプリは廃止され、Teams の[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)に置き換えられました。 患者アプリのデータは、チームを支援する Office 365 グループのグループ メールボックスに保存されます。 患者アプリに関連付けられているすべてのデータはこのグループに保持されますが、ユーザー インターフェイスからアクセスすることはできなくなります。 ユーザーは、[リスト アプリ](https://support.microsoft.com/office/get-started-with-lists-in-teams-c971e46b-b36c-491b-9c35-efeddd0297db)を使用してリストを再作成できます。
>
>リストを使用すると、医療機関のケア チームは、ラウンドや学際的なチーム会議から一般的な患者の監視に至るまでのシナリオで患者リストを作成できます。 開始するには、リストの患者テンプレートを確認してください。 組織でリスト アプリを管理する方法の詳細については、「[リスト アプリの管理](../../manage-lists-app.md)」を参照してください。

次の手順に従って、Azure API for FHIR Microsoft Teamsにアクセスできる、Azure の Patients アプリを許可します。 この記事では、テナントに [Azure API for FHIR インスタンス](https://azure.microsoft.com/services/azure-api-for-fhir/) が設定され、構成されていることを前提とします。  テナントに Azure API for FHIR インスタンスをまだ作成していない場合は、「クイック スタート: Azure portal を使用して Azure API for FHIR をデプロイする」 [を参照してください](/azure/healthcare-apis/fhir-paas-portal-quickstart)。

1. ここを [クリックして](https://login.microsoftonline.com/common/adminConsent?client_id=4aee3506-b263-43e0-ba31-1468fa7b2806) 、Patients アプリの管理者の同意を付与します。 メッセージが表示されたら、テナント管理者またはグローバル管理者の資格情報を使用してサインインし、[同意] をクリックして必要なアクセス許可を付与します。

    ![Patients アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request.png)

    承諾した後、ウィンドウを閉じます。 次のようなページが表示されます。 ページのエラー メッセージは無視できます。 これは無害であり、同意が与えらたかどうかを示します。 (この URL のより使い分け的なページに取り組み中です。 ご期待ください。

    ![Patients アプリのアクセス許可要求のスクリーンショット](../../media/patients-app-permissions-request-granted.png)

2. 管理者の資格情報 [を使用して Azure Portal](https://portal.azure.com) にサインインします。

3. 左側のナビゲーションで 、[アプリケーション]**をAzure Active Directory** し、[アプリケーション] **Enterprise選択します**。

    **Patients (dev) という名前の** 行を探し、[オブジェクト **ID]** 列の値をクリップボードにコピーします。

    ![Azure portal の患者 (開発) 行のスクリーンショット](../../media/patients-app-azure-portal-object-id.png)

4. (検索するか、リソースを参照して) Patients アプリを接続する Azure API for FHIR リソース インスタンスに移動し、そのインスタンスの設定を開きます。

    ![Azure portal での Azure API for FHIR インスタンス設定のスクリーンショット](../../media/patients-app-azure-portal-instance-settings.png)

5. [ **認証]** をクリックし、手順 3 でコピーしたオブジェクト ID を [許可された **オブジェクト ID] ボックスに貼り付** けます。 これにより、Patients アプリは FHIR サーバーにアクセスできます。 オブジェクト ID を貼り付Azure Active Directory検証すると、その横に緑色のチェック マークが表示されます。

    ![Azure portal の認証設定のスクリーンショット](../../media/patients-app-azure-portal-authentication.png)

6. **[保存]** をクリックします。 これにより、インスタンスが再デプロイされます。これには数分かかる場合があります。

7. [ **概要]** をクリックし、FHIR メタデータ エンドポイント **から URL をコピーします**。 メタデータ タグを削除して、FHIR サーバーの URL を取得します。 たとえば、 `https://test02-teamshealth.azurehealthcareapis.com/` です。

    ![Azure portal のメタデータ エンドポイント](../../media/patients-app-azure-portal-metadata-endpoint.png)

8. このTeams、チームに読み込まれている Patients アプリ インスタンスに移動し **、[設定]** をクリックし、[リンク] ボックスに FHIR サーバー エンドポイント URL を入力します。 次に **、[Connect]** をクリックして接続を確立し、患者を検索してリストに追加します。  

    ![ 患者アプリの設定 (Teams](../../media/patients-app-teams.png)

    この手順で Teams に接続するときにエラーが発生した場合は、エラーの詳細なスクリーンショット[、Fiddler](https://www.telerik.com/download/fiddler)からのログ、その他の再現手順を電子メールに送信し、件名行に "Patients App – EMR mode troubleshooting" を teamsforhealthcare@service.microsoft.com に送信[します。](mailto:teamsforhealthcare@service.microsoft.com)

## <a name="related-topics"></a>関連トピック

- [患者アプリの概要](patients-app-overview.md)
- [電子医療記録を Microsoft Teams に統合する](patients-app.md)