---
title: オーディオ会議ブリッジの設定を変更します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: '呼び出し元のメッセージを表示し、ビジネスまたはマイクロソフトのチームのアプリケーションの Skype を使用していないことと、名前と会議の開催者のピンを収集するために使用する会議用ブリッジの設定を変更する必要があります手順を取得します。 '
ms.openlocfilehash: c58c1b3031da9e9ebe8408568bed0fd4b8c9ae9b
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>オーディオ会議ブリッジの設定を変更します。

Office 365 に電話会議を設定する場合、オーディオ会議ブリッジと呼ばれますから、ユーザーの電話番号が表示されます。 会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。 これらの電話番号は、呼び出し元が、会議にダイヤルインするときに使用されます。 電話番号では、ビジネスまたはマイクロソフトのチームの会議出席依頼の Skype の下部に含まれています。
  
会議用ブリッジが呼び出しに応答し、会議自動アテンダント、およびその後、設定によってを使用して音声メッセージを呼び出し元を確認できます通知を再生、自分の名前を記録するための呼び出し元を確認、暗証番号 (pin) の設定を制御します。 ピンはされたミーティングの開催者に許可するように、会議を開始するが使用していない、Skype アプリのビジネスまたはマイクロソフトのチームにします。

  > [!IMPORTANT]
  > PIN がだけが必要なとき、Skype アプリケーション ユーザーのビジネスまたはマイクロソフトのチームの会議の開催者が会議を既に開始していません。 場合はすべてのユーザーがダイヤルイン会議、暗証番号 (pin) は会議の開催者、会議を開始する必要があります。 

> [!CAUTION]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="teams-logo-30x30pngimagesteams-logo-30x30png-using-the-microsoft-teams-and-skype-for-business-admin-center"></a>![チーム ・ ロゴ ・ 30x30.png](../images/teams-logo-30x30.png) ビジネス管理センターは、マイクロソフトのチームと Skype を使用してください。

1. 左側のナビゲーションでは、**会議**に移動 > **会議ブリッジ**です。 

2. **会議ブリッジ**のページの上部には、**ブリッジの設定**をクリックします。 

3. **ブリッジの設定**ウィンドウで、次のコマンドを選択します。 
  - **ミーティングのエントリと終了の通知**場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。
    
    **会議の開始と終了の通知**を有効にするときは、これらのオプションを選択できます。
    
  - **名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。
    
  - **トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。
      
  - **ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**このオプションをオフにすると場合、は、会議に参加する前に自分の名前を記録するための呼び出し元を求められますされません。

4. 会議の暗証番号 (pin) の長さを設定するには、**暗証番号 (pin) の長さ**] ボックスの一覧に PIN の桁数を選択します。

5. ユーザーに電子メールを送信するかどうかを指定するには、有効または**、オーディオ会議の構成が変更された場合、ユーザーに e メールを自動的に送信**を無効にします。
    詳細については、[電子メールは、ユーザーが電話会議の設定を変更するときに自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。
 
6. [**適用**] をクリックします。 
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--using-the-skype-for-business-admin-center"></a>![デバイス ・ ロゴ ・ 30x30.png](../images/sfb-logo-30x30.png)  Skype for Business 管理センターを使用する

 **呼び出し元がミーティングに参加するときに会議の経験を設定します。**
    
1. **ビジネス管理センターの Skype**では、左側のナビゲーションで移動**電話会議**に > **Microsoft ブリッジ設定**します。
    
2. **Microsoft ブリッジの設定**ページで、[**会議参加の経験**をするには、次のコマンドを選択します。
    
  - **Enable meeting entry and exit notifications to be turned on** This is selected by default. チェック ボックスをオフにするとデータを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。
    
    **会議エントリを有効にして終了の通知をオンにする**を選択すると、**開始/終了のお知らせの種類**] ボックスの一覧からこれらのオプションを選択します。
    
  - **名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。
    
  - **トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。
  
  - **会議の PIN の長さを設定する** チェック ボックスをオフにした場合は、会議に参加する前に自分の名前を記録する呼び出し元を求められますされません。
    
3. Sign in to Office 365 with your work or school account.
    
In the Skype for Business admin center, in the left navigation go to dial-in conferencingMicrosoft bridge settings.
  
1. PIN の桁数は 4 から 12 の間にする必要があります。既定値は 5 です。
    
2. Sign in to Office 365 with your work or school account.
    
3. 既定値は 5 です。
    
4. **Microsoft ブリッジの設定**] ページの [**セキュリティ**] の下に**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。
    
    > [!IMPORTANT]
    > The default is 5. 
  
**ユーザーに電子メールを送信するかどうかを選択します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. Sign in to Office 365 with your work or school account.
    
3. 既定値は 5 です。
    
4. **Microsoft ブリッジの設定**] ページで、選択や**ダイヤルイン情報を変更した場合、ユーザーに e メールを自動的に送信**を、し、[**保存**] をクリックします。
    
    詳細については、[電子メールは、ユーザーが電話会議の設定を変更するときに自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Go to the Office 365 admin centerSkype for Business.

- 時間を節約またはこのプロセスを自動化するには、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。
    
- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- 多くのユーザーの設定を同時に変更するときなどは、Office 365 管理センターのみを使用するよりも、Windows PowerShell の方に、速度、わかりやすさ、生産性の点で多くのメリットがあります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Lync Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議をセットアップする](set-up-audio-conferencing.md)
