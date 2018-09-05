---
title: 別の組織内のチームのユーザーとの通信します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection: Strat_MT_TeamsAdmin
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
description: ユーザーが別の組織内のユーザーと通信できるようにするのにはチームを構成する方法を参照してください。
ms.openlocfilehash: b8c3705b288abd81e85bd941ab019bb8e8e0e40e
ms.sourcegitcommit: 53c10589c284c6e4bbba574a7ba2df2d29519d1b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/05/2018
ms.locfileid: "23829115"
---
# <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>チームのユーザーのチャットを使用し、チームの別の組織内のユーザーとの通信

記事の場合この手順を使用します。
  
- お客様のビジネスの別のドメインにユーザーがあります。 たとえば、Rob@ContosoEast.com と Ann@ContosoWest.com です。
    
- チームを使用して特定の企業、組織外の人に連絡するのには、組織内には、人をします。
    
- 他のユーザーを検索し、連絡先、電子メール アドレスを使用することができるチームを使用している世界で。 他のユーザーは、外部アクセスを有効にして、他方のドメインを許可する、これは動作します。 動作しない場合は、他のユーザーを確認してください彼または彼女の構成は、ドメインをブロックされていません。

これらの手順に従います。

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-teams-organization"></a>チームのユーザーのチャットを使用し、チームの別の組織内のユーザーとの通信

### <a name="step-1---make-sure-to-set-up-the-ports-and-urls-that-are-needed"></a>手順 1 - ポートおよび必要な Url を設定することを確認します。

**企業間の通信を設定する際に発生する最も一般的な問題は、取得[Office 365 の Url と IP アドレスの範囲](https://docs.microsoft.com/en-us/microsoftteams/office-365-urls-ip-address-ranges)右です。**

### <a name="step-2---enable-your-organization-to-communicate-with-another-teams-organization"></a>手順 2 - 別のチームの組織と通信するために組織を有効にします。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチームとビジネス管理センターの Skype を使用します。**

   1. 左側のナビゲーションでは、**組織全体の設定**に移動 > **外部からアクセス**します。 

   2. **外部アクセス**] ページの上部には、**上**に**外部からのアクセス**をクリックします。 

   3. 許可リストに他の組織のドメインを追加するには、**追加のドメイン**をクリックします。 **ドメインの追加**] ウィンドウで、**許可**し、次に**行われる**ドメインの名前をクリックしてに配置します。

   4. 電話会議の設定を使用してユーザーにメールを送信することもできます。**** 

   5. その他のチームの組織の管理者は、同じ手順を確認します。 などの**ドメインを許可する**ボックスの一覧で、管理者が自社のドメインを入力する必要があります。

### <a name="step-3---test-it"></a>手順 3 - テスト
セットアップをテストするには、チームないユーザーが、ファイアウォールの背後にある必要があります。
  
   1. 組織の管理者が、**外部アクセス**の設定を変更された後に適切なはずです。
    
   2. チーム アプリケーションでは、電子メール アドレス、ユーザーの検索し、チャットするのには要求を送信します。
    
   3. チャットへの要求を送信するチーム メンバーに依頼します。 要求の場合、問題は、ファイアウォールの設定 (ファイアウォール設定が正しいことが既にわかっていると仮定した場合) です。
    
   4. 問題がお使いのファイアウォールであるかどうかをテストする別の方法ではないファイアウォールの内側に、コーヒー ショップなどの wifi の場所に移動し、チャットする相手に要求を送信するチームを使用します。 メッセージは、そこを通過し、問題がわかっていないしたら職場場合、は、お使いのファイアウォールです。

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Skype のオンライン ビジネスの組織内のユーザーとの通信します。

設定する場合はそれまでのように、チームのユーザーを見つけて、Skype のビジネス組織内にいるユーザーに問い合わせて、あなたは以下の手順には、その組織の管理者です。

![デバイスのロゴ-30x30.png](media/sfb-logo-30x30.png) **ビジネス管理センターの Skype を使用します。** 

組織は、次の手順を行うことで、管理者があります。
    
1. Office 365 管理センターで、[**管理センター**]  >  [**Skype for Business**] に移動します。
  
2. [**Skype for Business 管理センター**] で、[**組織**]  >  [**外部通信**] を選びます。
    
3. 設定するには、特定のビジネスで、または、ドロップ ダウン ボックスで、別のドメイン内のユーザーとの通信**にのみ許可されるドメイン**を選択します。
    
    ビジネス ポリシーでは、Skype の選択を開くには世界中の他のすべてとの通信を有効にするかどうか、または、**をブロックするドメインを除く**。 これは既定の設定です。
    
4. [**ブロックまたは許可するドメイン**] を選択して**+** を許可するドメインの名前を追加します。 他の組織内の管理者は、同じ手順を確認します。 などの**ドメインを許可する**ボックスの一覧で、管理者が自社のドメインを入力する必要があります。
    
### <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[チームの署名](sign-in-teams.md)
[エンド ・ ユーザーは、チームのトレーニング](enduser-training.md)

