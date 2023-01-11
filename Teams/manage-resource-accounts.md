---
title: Teams のリソース アカウントを管理する
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: この記事では、Microsoft Teams でリソース アカウントを作成、編集、管理する方法について説明します。
ms.openlocfilehash: 2bc0642f20341b9818b1c407fa0294127ee44d6a
ms.sourcegitcommit: ae687f530d5505b96df7cb7ef4da3a36bd9afd29
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/10/2023
ms.locfileid: "69763578"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a>Microsoft Teams のリソースのアカウントの管理

[!INCLUDE [set-up-resource-account-steps](./includes/set-up-resource-account-steps.md)]

## <a name="next-steps"></a>次の手順

リソース アカウントのセットアップを完了し、必要に応じて電話番号を割り当てると、自動応答または通話キューでリソース アカウントを使用する準備が整います。

詳細については、次の参照を参照してください。

- [クラウド自動応答](create-a-phone-system-auto-attendant.md)
- [クラウド呼び出しキュー](create-a-phone-system-call-queue.md)

[編集] オプションを使用して、リソース アカウント **の [表示名** ] と **[リソース アカウント** の種類 **] を編集** できます。 完了したら、[ **保存] を選択します** 。

## <a name="change-an-existing-resource-account-to-use-a-microsoft-teams-phone-resource-account-license"></a>Microsoft Teams 電話 リソース アカウント ライセンスを使用するように既存のリソース アカウントを変更する

既存のリソース アカウントのライセンスを Teams 電話スタンダード ライセンスから **Microsoft Teams 電話** **リソース アカウント** ライセンスに切り替えるには、**Microsoft Teams 電話 リソース アカウント** ライセンスを取得してから、[ユーザーを別の [サブスクリプションに移動する] を](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)Microsoft 365 管理センターします。

> [!WARNING]
> **Teams 電話スタンダード** ライセンスを常に削除し、同じライセンス アクティビティ **でMicrosoft Teams 電話リソース アカウント** ライセンスを割り当てます。 古いライセンスを削除し、アカウントの変更を保存し、新しいライセンスを追加してから、アカウント設定をもう一度保存すると、リソース アカウントが期待どおりに機能しなくなる可能性があります。 その場合は、**Microsoft Teams 電話 リソース アカウント** ライセンスの新しいリソース アカウントを作成し、壊れたリソース アカウントを削除することをお勧めします。

## <a name="skype-for-business-server-2019"></a>Skype For Business Server 2019

クラウド通話キューとクラウド自動応答で使用できる Skype For Business Server 2019 に所属するリソース アカウントについては、「 [クラウド通話キューの計画](/SkypeforBusiness/hybrid/plan-call-queue) 」または「 [クラウド自動応答の計画](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)」を参照してください。 ハイブリッド実装 (ダイレクト ルーティングに基づく番号) は、オンプレミスの Skype for Business Server 2019 サーバー上の [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) コマンドレットを使用して構成されます。

アプリケーション インスタンスの作成時に使用する必要があるアプリケーション ID は次のとおりです。

- **自動応答:** ce933385-9390-45d1-9512-c8d228074e07
- **通話キュー:** 11cd3e2e-fccb-42ad-ad00-878b93575e07

> [!NOTE]
> Skype For Business Server 2019 ユーザーが通話キューまたは自動応答を検索できるようにする場合は、オンライン リソース アカウントが Active Directory に同期されないため、Skype For Business Server 2019 でリソース アカウントを作成する必要があります。 sipfederationtls の DNS SRV レコードが 2019 Skype for Business Serverに解決される場合、リソース アカウントは SfB Management シェルを使用して Skype For Business Server 2019 で作成し、Azure AD に同期する **必要があります**。

Skype for Business Serverを使用したハイブリッド実装の場合:

- [クラウド自動応答を計画します](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)。
- [クラウド呼び出しキューを計画します](/SkypeforBusiness/hybrid/plan-call-queue)。
- [オンプレミスのリソース アカウントを構成します](/SkypeForBusiness/hybrid/configure-onprem-ra)。

## <a name="delete-a-resource-account"></a>リソース アカウントを削除する

電話番号を削除する前に、リソース アカウントから電話番号の関連付けを解除して、保留中のモードで電話番号がスタックしないようにしてください。

その後、Microsoft 365 管理センターの [**ユーザー**] タブでリソース アカウントを削除できます。

リソース アカウントからダイレクト ルーティング電話番号の関連付けを解除するには、次のコマンドレットを使用します。

```powershell
Remove-CsPhoneNumberAssignment -Identity <Resource Account Object ID> -PhoneNumber <assigned phone number> -PhoneNumberType DirectRouting
```

## <a name="hide-resource-accounts-from-teams-users"></a>Teams ユーザーからリソース アカウントを非表示にする

Teams ユーザーから特定のリソース アカウントを非表示にすることもできます。 たとえば、Teams ユーザーが通話キューを直接呼び出し、操作時間が構成されている自動応答をバイパスできないようにすることができます。

[情報バリアは、](information-barriers-in-teams.md) リソース アカウントを非表示にするために使用されます。  以下の手順に進む前に、情報バリアに関するドキュメントを参照して、考えられる影響を理解してください。

### <a name="required-subscriptions-and-permissions"></a>必要なサブスクリプションとアクセス許可 

情報バリアにアクセスして使用するには、組織に次のいずれかのサブスクリプションまたはアドオンが必要です。 

-   Microsoft 365 E5/A5 サブスクリプション (有料または試用版)。
-   Office 365 E5/A5/A3/A1 サブスクリプション (有料または試用版)。
-   アドオンをOffice 365 Advanced Complianceします。
-   Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 コンプライアンス アドオン。
- Microsoft 365 E3/A3/A1 サブスクリプション + Microsoft 365 E5/A5 Insider Risk Management アドオン。

> [!NOTE]
> [Exchange Online](/exchange/address-books/address-book-policies/address-book-policies)アドレス帳ポリシーが既に構成されている場合は、以下の手順に進む前に削除する必要があります。   
> 
> 以下のすべての手順は、テナント 全体管理者によって実行されます。 
>   
> これらの手順では、他の情報バリアが構成されていないことを前提としています。

#### <a name="teams-admin-center"></a>Teams 管理センター

1. [Teams 管理センター](https://go.microsoft.com/fwlink/p/?linkid=2066851)にサインインします。
2. 左側のレール メニューで、[Teams] を展開 **します**。
3. [ **Teams の設定] を選択します**。 
4. [ **名前で検索**] まで下にスクロールします。
5. トグルをオンにして、変更を保存します。

このオプションの詳細については、「 [Teams でディレクトリを検索するときにユーザーが表示できるユーザーを制限する](teams-scoped-directory-search.md)」を参照してください。

#### <a name="compliance---auditing"></a>コンプライアンス - 監査

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。
2. 左側のナビゲーション ウィンドウで、[監査] を選択 **します**。
3. 監査がオフになっている場合は、次のバナーが表示されます。 
 
     :::image type="content" source="/microsoft-365/media/AuditingBanner.png" alt-text="監査が有効になっていない場合の監査バナーを示すスクリーンショット":::
  
4. [ **ユーザーと管理者の記録の開始] アクティビティを選択します**。 

監査の詳細については、「 [Microsoft 365 で監査 (Standard) を設定する」](/microsoft-365/compliance/audit-standard-setup)を参照してください。

#### <a name="segmenting-data"></a>データのセグメント化

直接呼び出す必要がないリソース アカウントは、セグメント化され、簡単に識別できる必要があります。  これを行うには、特定のグループのメンバーにするか、ユーザー プロファイル内の次のような一意の情報を使用します。 

-   会社
-   ユーザー プリンシパル名
-   場所
-   部署
-   使用状況の場所
-   メールのニックネーム (エイリアス)
-   物理的な配送オフィス名 (Office)
-   郵便番号
-   プロキシ アドレス (Email アドレス)
-   番地
-   ターゲット アドレス (ExternalEmailAddress)
-   メール (WindowsEmailAddress)
-   説明

次の手順の例では、フィールドが `Department` 使用されます。 

ユーザーのセグメント化の詳細については、「セグメントの  [識別](/microsoft-365/compliance/information-barriers-policies)」を参照してください。

#### <a name="microsoft-admin-center"></a>Microsoft 管理センター

1. [Microsoft 365 管理 センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)にサインインします。
2. 左側のナビゲーション ウィンドウで、[ **アクティブ なユーザー**] を選択します。
3. 直接呼び出しをブロックする最初のリソース アカウントを選択します。
4. 右側のウィンドウで [ **連絡先情報の管理** ] を選択します。
5. フィールドの内容を `Department` 、部署名として使用されていない一意の単語または頭字語に置き換えます。 たとえば、 `DNC`です。
6. 変更を保存します。
7. 直接呼び出しの受信をブロックする必要があるリソース アカウントごとに、この手順を繰り返します。

#### <a name="compliance---information-barriers"></a>コンプライアンス - 情報バリア

1. [Microsoft Purview コンプライアンス ポータル](https://compliance.microsoft.com/)にサインインします。
2. 左側のナビゲーション ウィンドウで、[ **情報バリア** > **] [セグメント]** を選択します。
3. [ **新しいセグメント**] を選択します。
4. セグメントの名前を入力し、[ **次へ**] を選択します。 たとえば、 `Uncallable Resource Accounts`です。
5. [ **+ 追加] を選択** し、[部署] を **選択** します。
6. 上記の Microsoft 管理センターの手順 5 で使用した一意の単語または頭字語を入力します。 たとえば、 `DNC`です。
7. [ **次へ**] を選択し、[ **送信] を選択します**。
8. [ **新しいセグメント**] を選択します。
9. セグメントの名前を入力し、[ **次へ**] を選択します。 たとえば、 `Callable Users`です。
10. [ **+ 追加] を選択** し、[部署] を **選択** します。
11. [ **等しい** ] ドロップダウンを選択し、[ **等しくない**] を選択します。
12. 上記の Microsoft 管理センターの手順 5 で使用した一意の単語または頭字語を入力します。 たとえば、 `DNC`です。
13. [ **次へ**] を選択し、[ **送信] を選択します**。 
14. 左側のナビゲーション ウィンドウで、[**情報バリア** >  ポリシー] を選択 **します**。
15. [ **ポリシーの作成] を選択します**。
16. ポリシーの名前を入力し、[ **次へ**] を選択します。 たとえば、 `Uncallable Resource Accounts`です。
17. [ **+ セグメントの選択] を選択** し、上記の手順 9 で作成したセグメントを追加し、[ **次へ**] を選択します。 たとえば、 `Callable Users`です。
18. [**コミュニケーションとコラボレーション**] ドロップダウンから [**ブロック]** を選択します。
19. [ **+ セグメントの選択] を選択** し、上記の手順 4 で作成したセグメントを追加し、[ **次へ**] を選択します。 たとえば、 `Uncallable Resource Accounts`です。
20. ポリシーを **[オン]** に設定し、[ **次へ**] を選択し、[ **送信] を選択します**。
21. [ **ポリシーの作成] を選択します**。
22. ポリシーの名前を入力し、[ **次へ**] を選択します。 たとえば、 `Callable Users`です。
23. [ **+ セグメントの選択] を選択** し、手順 4 で作成したセグメントを追加し、[ **次へ**] を選択します。
24. [**コミュニケーションとコラボレーション**] ドロップダウンから [**ブロック]** を選択します。 
25. [ **+ セグメントの選択] を選択** し、上記の手順 9 で作成したセグメントを追加し、[ **次へ**] を選択します。
26. ポリシーを **[オン]** に設定し、[ **次へ**] を選択し、[ **送信] を選択します**。
27. 左側のナビゲーション ウィンドウで、[ **情報バリア** > **ポリシー アプリケーション**] を選択します。
28. [ **すべてのポリシーの適用] を選択します**。

> [!NOTE]
> ポリシーが適用されるまでに 30 分以上かかる場合があります。  
> 
> 状態が完了したら、Teams クライアントに移動し、ブロックされたリソース アカウントを検索します。 Teams キャッシュをクリアすることが必要な場合があります。  
> 
> Teams ユーザーがリソース アカウントを連絡先として保存した場合、そのユーザーは呼び出しできなくなります。
