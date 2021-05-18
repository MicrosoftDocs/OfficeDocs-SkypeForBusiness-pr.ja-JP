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
description: 'ユーザーが別の組織Skype for Businessユーザーと話したり、外部の連絡先がユーザーと話し合うのを許可したりするために、ユーザーを構成する方法を参照してください。 '
ms.openlocfilehash: 3b4aeb2b40cf34579d3d584a50664550cd34038c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240005"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>ユーザーが外部の Skype for Business ユーザーに連絡できるようにする

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
  
次の場合、この記事で説明する手順をご利用ください。
  
- ビジネスの異なるドメインにユーザーがいます。 たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。

- 組織内のユーザーが組織外の特定のSkype for Businessのユーザーに連絡するために、ユーザーを使用する必要があります。

- 世界中のユーザーがメール アドレスを使用してSkype for Businessを見つけて連絡したい場合。 ユーザーとユーザーが既定の設定を使用Skype for Business、この設定は自動的に機能します。 ブロックされていない場合は、構成によってドメインがブロックされていないことを確認する必要があります。

## <a name="enable-business-to-business-communications-for-your-users"></a>ユーザーの企業間通信を有効にする

<a name="bk_preview"> </a>

この通信を[行うには、](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)両方の組織Microsoft 365またはOffice 365管理者アクセス許可が必要です。

![管理センターを使用Microsoft Teams ](../images/teams-logo-30x30.png) **ロゴをTeamsアイコン**
  
1. 管理者アカウントを使用Microsoft 365またはOffice 365サインインします。

2. 管理センターで、[管理センター] に **移動Teams。**  >  

    ![[管理者] Teams選択します。](../images/MS-Teams-Admin.png)
  
3. [Teams **センターで、[レガ** シ **ポータルSkype** SfB レガシ ポータルの選択 >  
  ![ ] を選択します。](../images/SFBlegacy-size65.png)

4. **Skype for Business 管理センター** で、[**組織**]  >  [**外部通信**] の順に選択します。
5. 特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。

    または、Skype for Business ポリシーを開いている世界中の他のすべてのユーザーとの通信を有効にする場合は、ブロックされているドメインを除いて [オン] を **選択します**。 これは、既定の設定です。

6. [**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。

7. 他の組織の管理者が、管理センター で同じ手順 **を実行Skype for Business確認します**。 たとえば、相手の組織の管理者は、その組織の **許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。

8. ファイアウォールを使用している場合Windows必要Skype for Businessポートが自動的に開きます。

    組織が別のファイアウォール ソリューションを使用してネットワーク上のコンピューターがインターネットに接続されるのを制限している場合は、クライアント コンピューターが次の Office 365 URL と[IP](/microsoftteams/office-365-urls-ip-address-ranges)アドレス範囲 にアクセスできる必要があります。 これには、ファイアウォールまたはプロキシ インフラストラクチャの構成 **\* (.api.skype.com、.users.storage.live.com、** および の送信許可リストに FQDN を追加する必要 \* ****graph.skype.com。** これらのポートをファイアウォールで開く方法については、ファイアウォールに付属のドキュメントを確認してください。

    開く必要があるすべてのポートの一覧については、「URL と IP アドレス範囲Office 365[を参照してください](/microsoftteams/office-365-urls-ip-address-ranges)。

9. 組織の管理者もこれらの手順に従っている必要があります。

10. **テストするには、最大 24 時間待機します**。 外部通信設定を変更すると、変更がすべてのデータ センターに設定されるのに最大 24 時間かかる場合があります。

![](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png)Skype無料のコンシューマー アプリである Skype を使用しているすべてのユーザーと IM を検索および IM することができます。 詳細については、「ユーザーが連絡先を[追加Skype for Businessする」Skype参照してください](let-skype-for-business-users-add-skype-contacts.md)。
  
## <a name="test-and-troubleshoot"></a>テストとトラブルシューティング

<a name="bk_preview"> </a>

 **企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**
  
セットアップをテストするには、会社のファイアウォールの背後にSkype for Businessの連絡先が必要です。
  
1. 外部通信の設定を変更した後、テスト **するまで最大 24 時間待ちます**。

2. このSkype for Businessで連絡先を検索しSkype for Businessチャットに要求を送信します。

    会社のポリシーが原因で送信できなかったというメッセージが表示された場合は、OFFICE 365 URL と IP アドレス範囲を確認[する必要があります](/microsoftteams/office-365-urls-ip-address-ranges)。

3. 他のSkype for Businessに、チャットのリクエストを送信してください。 相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。

4. 問題がファイアウォールであるかどうかをテストするもう 1 つの方法は、コーヒー ショップなどのファイアウォールの背後ではない Wi-Fi の場所に移動する方法です。 [Skype for Businessを使用して、連絡先にチャットに要求を送信します。 メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。

## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>別のビジネスに接続するときに、他のユーザーを見つけて見つける方法

<a name="bk_preview"> </a>

他のユーザーとの外部通信を有効Skype for Business、ユーザーはサインイン名を検索Skype for Businessフェデレーション ユーザーを検索できます。 たとえば、次 Rob@contoso.com。 その後、連絡先のリストにユーザーを追加する必要があります。
  
![フェデレーションビジネスのユーザーを見つけるには、そのユーザーのメール アドレスを検索する必要があります (通常はサインイン名です)。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>ヒントとの通信の設定に関する詳細

<a name="bk_preview"> </a>

- Skype for Business 2015 と Skype for Business Online の間のフェデレーションを構成するには、「Skype for Business Online とのフェデレーション[の構成」を参照してください](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。

- Lync と Skype for Business Online の間のフェデレーションを構成するには、「Lync Online 顧客のフェデレーション サポートの[構成」を参照してください](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-federation-support-for-a-lync-online-customer)。

- Microsoft 365 または Office 365 の 2 人のユーザーが別々のドメインで互いに通信している場合、両方の組織で有効になっている Skype for Business 機能 (ビデオ会話やデスクトップ共有など) のみを使用できます。 Skype for Business

- 組織内の Skype for Business ユーザーが In-Place または訴訟ホールドに設定されている場合、そのユーザーと他の Skype for Business または Skype ユーザーの間の IM 会話は、メールボックスの回復可能なアイテムに保存されます。 これらの会話は、メールボックスの **[会話履歴]** フォルダーには保存されません。

## <a name="turn-off-external-communication-for-specific-individuals"></a>特定の個人の外部通信をオフにする

<a name="bk_preview"> </a>

ビジネス全体の外部通信を有効にした後は、特定の個人に対してオフにできます。
  
1. 管理者アカウントを使用Microsoft 365またはOffice 365サインインします。

2. 管理センターで、[ユーザー] [アクティブな **ユーザー]**  >  **に移動します**。

3. ユーザーの一覧でユーザーを選択し、[その他の設定] で 、[プロパティの設定を **クリックSkype for Businessします**。

    ![[Skype for Business](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. [管理 **センター] Skype for Business、[外部** 通信]**を選択します**。

    [オプション **] ページ** で、すべての選択肢が選択されます。 無効にする通信をクリアします。 次の図は、Jakob が他の信頼できる企業のユーザーと通信できますが、他のユーザーと通信Skype示しています。

    ![[外部連絡先] を選択する](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. [ **保存**] を選びます。

> [!NOTE]
> 変更が有効なまで最大 24 時間待機する必要がある場合があります。
  
[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>関連項目

<a name="bk_preview"> </a>

[Skype for Business Online をセットアップする](set-up-skype-for-business-online.md)
  
[Skype for Business ユーザーが Skype の連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
