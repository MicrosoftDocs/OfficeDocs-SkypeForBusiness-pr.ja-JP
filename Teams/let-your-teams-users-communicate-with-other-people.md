---
title: 他の組織の Teams ユーザーとの通信
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 09/12/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.audience: Admin
search.appverid: MET150
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: ms.teamsadmincenter.externalaccess.overview
description: ユーザーが別の組織のユーザーと通信できるように Teams を構成する方法を説明します。
ms.openlocfilehash: c3faf65dd3f36c193a75e74e73d90bf5e9be11df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222372"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする

次の場合、この記事で説明する手順をご利用ください。
  
- 社内の複数のドメインにユーザーがいる場合。 たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com のような場合。
    
- 組織内のユーザーが特定の組織外の会社のユーザーと連絡する際に、Teams を使用させたい場合。
    
- ユーザーのメール アドレスを使用して、世界中の Teams のユーザーは誰でもそのユーザーを検索して連絡を取れるようにする場合。 これは、ユーザーともう 1 人のユーザーの両方が外部アクセスを有効にしてお互いのドメインを許可している場合に可能になります。 正常に動作しない場合は、もう 1 人のユーザーの構成でユーザーのドメインがブロックされていないかを確認してもらいます。

こうすることで、他のユーザーがユーザーを検索し、ユーザーと通話し、インスタント メッセージを送信し、ユーザーとの会議を設定できるようになります。 外部のユーザーがチームとチャネルにアクセスできるようにする場合に適した方法は、ゲスト アクセスです。 この記事の手順に従って[ゲスト アクセスを有効にする](set-up-guests.md)と、ユーザーが通信できるようになります。

> [!IMPORTANT]
> 現在、組織外部の現在 AAD/テナントのゲストではない外部ユーザーに Microsoft Teams クライアント内でフェデレーションするには、ハイブリッド環境が正しく設定され、Skype for Business Online へ移行してある必要があります。 2019 年 2 月 25 日現在、SIP プロフィールのユーザーが Skype for Business Online に属している場合を除き、Teams ではネイティブのフェデレーションはまだサポートされていません。 ハイブリッド環境でアカウントを設定した後に Teams に移行する場合の詳細については、「[Skype for Business のハイブリッド展開を Teams にアップグレードする](https://docs.microsoft.com/ja-JP/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid)」を参照してください。

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>Teams のユーザーが別の Teams 組織のユーザーとチャットおよび通信できるようにする

以下の手順を実行します。

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>手順 1 - 必要なポートと URL を正しく設定します。

**企業間の通信を設定する場合に最もよく発生する問題は、[Office 365 の URL と IP アドレスの範囲](https://docs.microsoft.com/microsoftteams/office-365-urls-ip-address-ranges)の設定ミスによるものです。**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>手順 2 - 組織が別の Teams の組織と通信できるようにする設定

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Microsoft Teams 管理センターを使用する**

   1. 左側のナビゲーションで、[**組織全体の設定**]  >  [**外部アクセス**] に移動します。 

   2. [**外部アクセス**] ページの上部で、[**外部アクセス**] をクリックして [**オン**] にします。 

   3. すべての Teams の組織に対して、組織内のユーザーとの通信を許可する場合は、手順 5 に進みます。 
   
   4. 組織内のユーザーと通信できる組織を制限する場合は、特定のドメイン以外のすべての組織を許可する方法と、特定の組織のみを許可する方法とがあります。 特定のドメイン以外のすべての組織を許可するには、[**ドメインの追加**] をクリックしてブロックするドメインを追加します。 [**ドメインの追加**] ウィンドウで、ドメイン名を入力して [**ブロック**] をクリックし、[**完了**] をクリックします。  通信を特定の組織に制限するには、それらの組織のドメインを [**許可**] の状態でリストに追加します。 [許可] リストにいずれかのドメインを追加すると、他の組織との通信は、[許可] リストにドメインが表示される組織との通信のみに制限されます。 
   
   5. [**保存**] をクリックします。 

   6. 他の Teams の組織の管理者も同じ手順を実行したことを確認します。 たとえば、ある他の組織でその組織のユーザーと通信できる組織を制限している場合は、その組織の管理者は、**許可されたドメイン**のリストにお客様の会社のドメインを入力する必要があります。 

### <a name="step-3---test-it"></a>手順 3 - テスト
設定をテストするには、組織のファイアウォールの外側にいる Teams ユーザーが必要です。
  
   1. お客様ともう 1 つの組織の管理者が [**外部アクセス**] 設定の変更をそれぞれ完了すると、テストを開始できます。
    
   2. Teams アプリで、メール アドレスを使用してユーザーを検索し、チャットの要求を送信します。
    
   3. お客様宛にチャットの要求を送信するよう、Teams の連絡先に依頼します。 相手からの要求を受信できない場合は、お客様のファイアウォールの設定に問題があります (相手のファイアウォールの設定が正しいことが確認済みであることが前提)。
    
   4. 問題の原因がお客様のファイアウォールかどうかを別の方法でテストするには、ファイアウォールの外側の WiFi エリア (喫茶店など) へ行き、Teams を使用して連絡先にチャットの要求を送信します。 メッセージをその場所からは送信できる一方、職場からは送信できない場合は、問題の原因は職場のファイアウォールであることが特定できます。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Skype for Business Online の組織のユーザーとの通信

お客様の組織の Teams ユーザーが、組織のユーザーに連絡できる相手を制限している Skype for Business Online の組織のユーザーを検索して連絡できる設定になっている場合は、その組織の管理者に次の手順の実行を依頼します。

![sfb-logo-30x30.png](media/sfb-logo-30x30.png) **Skype for Business 管理センターを使用する** 

その組織の管理者に、次の手順を実行するよう依頼します。
    
1. Office 365 管理センターで、[**管理センター**]  >  [**Teams & Skype**]  >  [**従来のポータル**] の順に移動します。
  
2. **Skype for Business 管理センター**で、[**組織**]  >  [**外部通信**] の順に選択します。
    
3. 特定の会社や別のドメインのユーザーとの通信を設定するには、ドロップダウン ボックスで [**許可したドメインに対してのみオンにする**] を選択します。
    
    または、Skype for Business のオープン ポリシーを使用する世界中の誰とでもユーザーが通信できるようにするには、[**禁止したドメインを除いてオンにする**] を選択します。 これは、既定の設定です。
    
4. [**禁止したドメインまたは許可したドメイン**] の下で [**+**] を選択し、許可するドメイン名を追加します。 相手の組織の管理者も同じ手順を実行たことを確認します。 たとえば、相手の組織の管理者は、その組織の**許可されたドメイン** のリストにお客様の会社のドメインを入力する必要があります。
    
### <a name="related-topics"></a>関連トピック

[Microsoft Teams へのサインイン](sign-in-teams.md)
[Microsoft Teams のエンド ユーザー トレーニング](enduser-training.md)

