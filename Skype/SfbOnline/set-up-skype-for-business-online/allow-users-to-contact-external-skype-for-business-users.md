---
title: ユーザーが外部の Skype for Business ユーザーに連絡できるようにする
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
- LIL_Placement
description: 'Skype for Business を構成して、ユーザーが別の組織のユーザーと話したり、外部の連絡先に連絡を取らせたりする方法をご覧ください。 '
ms.openlocfilehash: 8acab73fec7337ee70cd8b5059b00df42e836e62
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093511"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>ユーザーが外部の Skype for Business ユーザーに連絡できるようにする
  
次の場合、この記事で説明する手順をご利用ください。
  
- お客様のビジネスには、さまざまなドメインのユーザーがいます。 たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。

- 組織内のユーザーが Skype for Business を使用して、組織外の特定の企業のユーザーと連絡を取る必要がある場合。

- Skype for Business を使用している世界中の他のユーザーが、自分のメール アドレスを使用して自分を見つけて連絡したい場合。 自分と他のユーザーが既定の Skype for Business 設定を使用している場合、この設定は自動的に機能します。 ブロックされていない場合は、構成によってドメインがブロックされていないことを確認する必要があります。

## <a name="enable-business-to-business-communications-for-your-users"></a>ユーザーに対して企業間の通信を有効にする

<a name="bk_preview"> </a>

この通信を行 [うには](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) 、Microsoft 365 または Office 365 の管理者権限が必要です。

![Teams 管理センターを使用する Microsoft Teams ](../images/teams-logo-30x30.png) **ロゴを示すアイコン**
  
1. Microsoft 365 または Office 365 管理者アカウントでサインインします。

2. 管理センターで、管理センター **の Teams に移動**  >  **します**。

    ![Teams 管理者を選択します。](../images/MS-Teams-Admin.png)
  
3. Teams センター **で、[Skype** レガシ **ポータル]** > **を選択し** 
  ![ 、SfB レガシ ポータルを選択します。](../images/SFBlegacy-size65.png)

4. **Skype for Business 管理センター** で、[**組織**]  >  [**外部通信**] の順に選択します。
5. 特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。

    または、Skype for Business ポリシーを開いている世界中の他のすべてのユーザーとの通信を有効にする場合は、ブロックされたドメインを除いて [オン] を **選択します**。 これは、既定の設定です。

6. [**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。

7. 他の組織の管理者が、Skype for Business 管理センターで同じ **手順を実行します**。 たとえば、相手の組織の管理者は、その組織の **許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。

8. Windows ファイアウォールを使用している場合は、Skype for Business によって必要なポートが自動的に開きます。

    組織が別のファイアウォール ソリューションを使用してネットワーク上のコンピューターのインターネットへの接続を制限している場合は、クライアント コンピューターが次の [Office 365 URL](/microsoftteams/office-365-urls-ip-address-ranges)と IP アドレス範囲にアクセスできる必要があります。 これには、ファイアウォールまたはプロキシ インフラストラクチャ構成の送信許可リストに FQDN を追加する必要がある場合があります。.api.skype.com、.users.storage.live.com、graph.skype.com。 **\*** \* **  ファイアウォールでこれらのポートを開く方法については、付属のドキュメントを確認してください。

    開く必要があるすべてのポートの一覧については [、365](/microsoftteams/office-365-urls-ip-address-ranges)個Office IP アドレス範囲を参照してください。

9. 組織の管理者も次の手順に従っている必要があります。

10. **テストするには、最大 24 時間待機します**。 外部通信の設定を変更すると、変更がすべてのデータ センターに適用されるのに最大 24 時間かかる場合があります。

![Skype では、無料のコンシューマー アプリである Skype を使用しているすべてのユーザーと、ユーザーが検索して ](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) IM を実行できます。 詳細については [、「Skype for Business ユーザーが Skype 連絡先を追加する」を参照してください](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>テストとトラブルシューティング

<a name="bk_preview"> </a>

 **企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**
  
セットアップをテストするには、会社のファイアウォールの背後にない Skype for Business の連絡先が必要です。
  
1. 外部通信の設定を変更した後、テストには最大 **24 時間待機します**。

2. Skype for Business で、Skype for Business で連絡先を検索し、チャットする要求を送信します。

    会社のポリシーが原因で送信できなかったというメッセージが表示された場合は、Office [365 の URL](/microsoftteams/office-365-urls-ip-address-ranges)と IP アドレス範囲を確認する必要があります。

3. Skype for Business の連絡先にチャットのリクエストを送信してください。 相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。

4. 問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、コーヒー ショップなど、ファイアウォールの背後ではない WiFi の場所に移動する方法です。 Skype for Business を使用して、連絡先にチャット要求を送信します。 メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>別のビジネスに接続するときに、他のユーザーを見つけて見つける方法

<a name="bk_preview"> </a>

他の Skype for Business ユーザーとの外部通信を有効にした後、ユーザーはサインイン名を検索してフェデレーション Skype for Business ユーザーを検索できます。 たとえば、次 Rob@contoso.com。 その後、ユーザーを連絡先のリストに追加する必要があります。
  
![フェデレーションビジネスでユーザーを見つけるには、そのユーザーのメール アドレス (通常はサインイン名) を検索する必要があります。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>フェデレーションビジネスとの通信のセットアップに関するヒント

<a name="bk_preview"> </a>

- Skype for Business 2015 と Skype for Business Online 間のフェデレーションを構成するには、次の記事を参照してください。Skype for Business Online とのフェデレーション [を構成します](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。

- Lync と Skype for Business Online 間のフェデレーションを構成するには、次の記事を参照[してください。](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)

- Microsoft 365 または Office 365 の 2 人の Skype for Business ユーザーが別々のドメインで互いに通信している場合、両方の組織で有効になっている Skype for Business 機能 (ビデオ会話やデスクトップ共有など) のみを使用できます。

- 組織内の Skype for Business ユーザーが In-Place または訴訟ホールドに設定されている場合、そのユーザーと他の Skype for Business または Skype ユーザー間の IM 会話は、メールボックスの回復可能なアイテムに保存されます。 これらの会話は、メールボックスの **[会話履歴** ] フォルダーには保存されません。

## <a name="turn-off-external-communication-for-specific-individuals"></a>特定の個人の外部通信をオフにする

<a name="bk_preview"> </a>

組織全体の外部通信を有効にした後は、特定の個人に対してだけオフにできます。
  
1. Microsoft 365 または Office 365 管理者アカウントでサインインします。

2. 管理センターで、[アクティブなユーザー ]  >  **に移動します**。

3. ユーザーの一覧でユーザーを選び、[その他の設定] で **[Skype for Business** のプロパティの編集] をクリックします。

    ![Skype for Business を選ぶ](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. Skype **for Business 管理センターで、[外部** 通信] **を選択します**。

    [オプション **] ページ** で、すべての選択肢が選択されます。 無効にする通信をクリアします。 次の画像は、Jakob が他の信頼できる企業のユーザーと通信できますが、他の Skype ユーザーと通信できない場合を示しています。

    ![外部連絡先を選択する](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. [ **保存**] を選びます。

> [!NOTE]
> 変更が有効にするまで、最大 24 時間かかる場合があります。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>関連項目

<a name="bk_preview"> </a>

[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)
  
[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
