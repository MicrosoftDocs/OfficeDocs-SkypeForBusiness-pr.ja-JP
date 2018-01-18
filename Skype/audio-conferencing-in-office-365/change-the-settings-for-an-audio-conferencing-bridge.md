---
title: "オーディオ会議ブリッジの設定を変更します。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: "呼び出し元のメッセージを表示し、クライアントのビジネスの Skype を使用していないことと、名と会議の開催者のピンを収集するために使用されるマイクロソフトでは、ダイヤルイン会議ブリッジの設定を変更する必要があります手順を取得します。 "
ms.openlocfilehash: 5da33e083999f00d217a86455f61fd58ca2d1713
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>オーディオ会議ブリッジの設定を変更します。

Office 365 に電話会議を設定する場合、オーディオ会議ブリッジと呼ばれますから、ユーザーの電話番号が表示されます。 会議用ブリッジは、1 つまたは複数の電話番号を含めることができます。 これらの電話番号は、呼び出し元が、会議にダイヤルインするときに使用されます。 電話番号では、ビジネスまたはマイクロソフトのチームの会議出席依頼の Skype の下部に含まれています。
  
会議用ブリッジが呼び出しに応答し、会議自動アテンダント、およびその後、設定によってを使用して音声メッセージを呼び出し元を確認できます通知を再生、自分の名前を記録するための呼び出し元を確認、暗証番号 (pin) の設定を制御します。 ピンはされたミーティングの開催者に許可するように、会議を開始するが使用していない、Skype アプリのビジネスまたはマイクロソフトのチームにします。

    > [!IMPORTANT]
    > A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting. If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting. 
  
## <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>オーディオ会議ブリッジの設定を変更します。

 **呼び出し元がミーティングに参加するときに会議の経験を設定します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **ビジネス管理センターの Skype**では、左側のナビゲーションで移動**電話会議**に > **Microsoft ブリッジ設定**します。
    
4. **Microsoft ブリッジの設定**ページで、[**会議参加の経験**をするには、次のコマンドを選択します。
    
  - **会議エントリを有効にして終了の通知をオンにする**これがデフォルトで選択されます。 チェック ボックスをオフにするとデータを入力したり、会議を離れると、会議に参加しているユーザーが通知はありません。
    
    **会議エントリを有効にして終了の通知をオンにする**を選択すると、**開始/終了のお知らせの種類**] ボックスの一覧からこれらのオプションを選択します。
    
  - **名前や電話番号**ユーザーが会議にダイヤルインするときは、それに参加するときに、電話番号が再生されます。
    
  - **トーン**ユーザーが会議にダイヤルインするときは、それに参加するときに、オーディオの音が再生されます。
    
    > [!NOTE]
    > **トーン**を使用して、お知らせの種類としては、すべてのお客様には、現在利用可能なプレビュー機能として。
  
  - **ミーティングに参加する前に自分の名前を記録する呼び出し元を確認**これがデフォルトで選択されます。 チェック ボックスをオフにした場合は、会議に参加する前に自分の名前を記録する呼び出し元を求められますされません。
    
5. 変更を行ったら、[**保存**] をクリックします。
    
**会議の暗証番号 (pin) の長さを設定します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. **Microsoft ブリッジの設定**] ページの [**セキュリティ**] の下に**暗証番号 (pin) の長さ**] ボックスの一覧で、[暗証番号 (pin) に使用桁の番号を入力し、し、[**保存**] をクリックします。
    
    > [!IMPORTANT]
    > 暗証番号 (pin) は、4 桁から 12 桁の間である必要があります。 
  
**ユーザーに電子メールを送信するかどうかを選択します。**
  
1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. **Microsoft ブリッジの設定**] ページを選択や**、オーディオ会議の構成が変更された場合、ユーザーに e メールを自動的に送信**するには、オフにし、[**保存**] をクリックします。
    
    詳細については、[電子メールは、ユーザーが電話会議の設定を変更するときに自動的に送信](emails-sent-to-users-when-their-settings-change.md)を参照してください。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約またはこのプロセスを自動化するには、[セット CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686 )コマンドレットを使用することができます。
    
- Windows PowerShell は、ユーザーを管理するユーザーを許可または許可されません。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
  - [Office 365 の PowerShell を使用する必要がある理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなど、Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点について学習します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Skype for Business Online 用 Windows PowerShell モジュールでは、リモート Windows PowerShell セッションを作成して Skype for Business Online に接続できます。このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「[Skype for Business Online 用 Windows PowerShell モジュール](https://go.microsoft.com/fwlink/?LinkId=294688)」からダウンロードできます。
  
## <a name="related-topics"></a>関連トピック

[Skype for Business および Microsoft Teams の電話会議のセットアップ](set-up-audio-conferencing.md)

