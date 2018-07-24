---
title: 外部の Skype for Business ユーザーに連絡できるようにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: b414873a-0059-4cd5-aea1-e5d0857dbc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- For O365M_ShareLync
- ms.lync.lac.OrgExternalAccess
- ms.lync.lac.skypefederation
- O365E_HRCLYNC _ SipFederationSrvRecordVerified_FL312122
- O365E_ShareLync
- O365M_ShareLync
- O365P_ExternalCommDesc
- O365P_ShareLync
ms.custom:
- Setup
- LIL_Placement
description: 'ユーザーが別の組織内のユーザーに問い合わせるか、外にそれらの連絡先を使用できるようにするのにはビジネス用の Skype を構成する方法を参照してください。 '
ms.openlocfilehash: bd03e7c85b91bb9995dcbac3fc5d885cba2c7bd0
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20968462"
---
# <a name="allow-users-to-contact-external-skype-for-business-users"></a>外部の Skype for Business ユーザーに連絡できるようにする

> [!NOTE]
> ビジネス連合の Skype を 21Vianet と Office 365 のドイツの組織によって運営されて Office 365 を使用できません。 
  
記事の場合この手順を使用します。
  
- ビジネスで別のドメインにユーザーがあります。 たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com です。
    
- ビジネス用の Skype を使用して特定の企業、組織外の人に連絡するのには、組織で人をします。
    
-する他のユーザーを検索し、連絡先、電子メール アドレスを使用することができるビジネス用の Skype を使用している世界で。 Skype のデフォルトを使用して、ビジネスの設定を自動的にこの動作はします。 しない場合は、ドメインの構成によってブロックされていないかどうかを確認する必要があります。
    
## <a name="enable-business-to-business-communications-for-your-users"></a>ユーザーの企業間の通信を有効にします。
<a name="bk_preview"> </a>

これを行う 2 つの組織で Office 365 の[管理者のアクセス許可](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d)が必要です。

![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Skype for Business の管理センターを使用する**
  
1. Office 365 管理者アカウントでサインインします。 
    
2. Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。
    
    ![Choose the Skype for Business admin center.](../images/376a7a45-e6e3-4716-be09-d2f294d885a2.png)
  
3. [**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。
    
4. 設定するには、特定のビジネスで、または、ドロップ ダウン ボックスで、別のドメイン内のユーザーとの通信**にのみ許可されるドメイン**を選択します。
    
    ビジネス ポリシーでは、Skype の選択を開くには世界中の他のすべてとの通信を有効にするかどうか、または、**をブロックするドメインを除く**。 これは既定の設定です。
    
5. [**ブロックまたは許可するドメイン**] を選択して**+** を許可するドメインの名前を追加します。
    
6. その他の組織の管理者には、**ビジネス管理センターの Skype**では、次の同じ手順を確認します。 などの**ドメインを許可する**ボックスの一覧で、管理者が自社のドメインを入力する必要があります。
    
7. Windows Firewall を使用している場合は、Skype for Business が必要なポートを自動的に開きます。
    
    組織がインターネットへの接続をネットワーク上のコンピューターを制限する別のファイアウォール ソリューションを使用している場合は、クライアント コンピューターは、次の[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)にアクセスすることを確認します。 インフラストラクチャの構成、ファイアウォールやプロキシのリストを許可する、送信する Fqdn を追加することがあります:**\*です。 api.skype.com**、 \***です。 users.storage.live.com**、と**graph.skype.com**。 お使いのファイアウォールでポートを開く方法の詳細については、それに付属のマニュアルを確認してください。
    
    すべてのポートを開く必要のリストは、 [Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を参照してください。

8. 管理者は、組織では、次の手順の後にもことを確認します。
    
9. **テストのために最大 24 時間待機します** 。外部通信設定を変更したときはいつでも、変更がデータ　センター全体に行き渡るまでに最大 24 時間かかる場合があります。
    
![Skype](../images/58550720-2a68-42d1-a926-1884e6aeb55c.png) Skype、無料のコンシューマー アプリケーションを使用して他のユーザーと IM を検索して、ユーザーを許可します。 詳細については、[ビジネス ユーザー向けの Skype は、Skype 連絡先を追加する](let-skype-for-business-users-add-skype-contacts.md)を参照してください。
  
## <a name="test-and-troubleshoot"></a>テストとトラブルシューティング
<a name="bk_preview"> </a>

 **企業間の通信を設定する際に発生する最も一般的な問題は、取得[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)右です。**
  
設定をテストするには、企業ファイアウォールの背後にあるではないビジネスの Skype の連絡先が必要です。
  
1. 外部通信設定を変更した後、 **テストのために最大 24 時間待機** します。
    
2. ビジネスの Skype は、ビジネス用の Skype の連絡先の検索でチャットへの要求を送信します。
    
    会社のポリシーのために送信できませんでしたというメッセージが表示される場合[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)を再確認する必要があります。
    
3. チャットへの要求を送信するビジネス用連絡先の Skype を依頼してください。 要求の場合、問題は、ファイアウォールの設定 (ファイアウォール設定が正しいことが既にわかっていると仮定した場合) です。
    
4. 問題がお使いのファイアウォールであるかどうかをテストする別の方法ではないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、チャットする相手に要求を送信するのにはビジネス用の Skype を使用します。 メッセージは、そこを通過し、問題がわかっていないしたら職場場合、は、お使いのファイアウォールです。
    
## <a name="how-to-find-others-and-be-found-when-connecting-with-another-business"></a>、他のユーザーを検索し、別のビジネスに接続するときを検出する方法
<a name="bk_preview"> </a>

ビジネス ユーザー向けの他の Skype での外部の通信を有効にした後、ユーザーは検索できます連合 Skype ビジネス ユーザー向けのサインイン名を検索し、: 例えば、Rob@contoso.com。 連絡先の一覧にユーザーを追加する必要があります。
  
![連合ビジネスでユーザーを検索するのには (これは、通常も、サインイン名)、電子メール アドレスを検索する必要があります。](../images/20242f85-0636-463b-8df3-1e123784d7fa.png)
  
## <a name="tips-on-setting-up-communications-with-federated-businesses"></a>連合の企業との通信設定のヒント
<a name="bk_preview"> </a>

- ビジネス 2015年の Skype と Skype のオンライン ビジネスとの間のフェデレーションを構成するには、この資料を参照してください:[ビジネス オンラインの Skype でフェデレーションを構成](https://technet.microsoft.com/en-us/library/jj205126.aspx)します。
    
- オンライン ビジネスの Lync と Skype との間のフェデレーションを構成するには、この資料を参照してください: [Lync のオンライン ・ カスタマーのフェデレーション サポートを構成します](https://technet.microsoft.com/en-us/library/hh202193.aspx)。
    
- Office 365 のビジネス ユーザー向けの 2 つの Skype は別のドメインに相互通信している場合 (たとえば、ビデオの会話またはデスクトップの共有) の両方の組織内有効になっているビジネス機能の Skype のみ使用できます。
    
- 埋め込みまたは証拠保全に、組織内のビジネス ユーザーは、Skype を配置すると、自分のメールボックスの**回復可能な項目**でそのユーザーとその他の Skype をビジネスまたは Skype のユーザーの間ですべての IM 会話が保存されます。 これらの会話は、自分のメールボックスの**会話履歴**フォルダーに保存されません。
    
## <a name="turn-off-external-communication-for-specific-individuals"></a>特定の個人の外部通信をオフにします。
<a name="bk_preview"> </a>

全体のビジネスでは、外部の通信を有効にした後は、特定の個人の無効にすることができます。
  
1. Office 365 管理者アカウントでサインインします。
    
2. **ユーザー**には、Office 365 管理センターで、 > **アクティブなユーザー**です。
    
3. 、ユーザーの一覧で、ユーザーの選択し、[**詳細設定**]**プロパティをビジネスの Skype を編集**] をクリックします。
    
    ![Skype をビジネスを選択します。](../images/2b0f9a7b-3fee-4f4b-968a-68c429eeb395.png)
  
4. **ビジネス管理センターの Skype**では、**外部の通信**を選択します。
    
    [**オプション**] ページで、すべての選択肢が選択されます。 通信を無効にするをオフにします。 次の図は、Jakob がその他の Skype ユーザーではなく、信頼されているその他の企業のユーザーと通信できることを示しています。
    
    ![外部の連絡先を選択します。](../images/4e546321-a065-48ed-8ac7-1e112a780eab.png)
  
5. [ **保存**] を選びます。
    
> [!NOTE]
> 変更を有効にするには、最大で 24 時間待機する必要があります。 
  


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
   
   
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。
<a name="bk_preview"> </a>

[Skype for Business Online のセットアップ](set-up-skype-for-business-online.md)
  
[Skype for Business ユーザーが Skype 連絡先を追加できるようにする](let-skype-for-business-users-add-skype-contacts.md)
  
  
 
