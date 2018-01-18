---
title: "会議に参加するときに自分の名前を記録するようにユーザーを有効にします。"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: "有効にするか、ユーザーが会議に参加するときの名前を記録できるかどうかを無効にする方法を学習します。 "
ms.openlocfilehash: f07bb24530e7b59ab6f54dfe2cd4eadf91def20c
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2017
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting"></a>会議に参加するときに自分の名前を記録するようにユーザーを有効にします。

Office 365 に電話会議を設定する場合の電話番号と、オーディオ会議ブリッジと呼ばれるが表示されます。 会議用ブリッジは、専用または共有の電話番号は、1 つまたは複数の電話番号を含めることができます。
  
会議用ブリッジの電話を使用して会議にダイヤルインするユーザーが呼び出しに応答します。 会議用ブリッジは、自動応答から音声メッセージを呼び出し元に回答し、それらの設定によって再生できる通知、呼び出し元が自分の名前を記録し、会議の開催者の暗証番号 (pin) のセキュリティを設定するに問い合わせてください。 ピンは、会議の開始を許可するように、ミーティングの開催者に与えられます。 ただし、ことができますを設定すると、暗証番号 (pin) が会議を開始する必要はありませんので。
  
## <a name="set-whether-callers-should-record-their-name"></a>呼び出し元が自分の名前を記録するかどうかを設定します。

1. 職場または学校のアカウントを使用して、Office 365 にサインインします。
    
2. **Office 365 管理センター**を参照して > **ビジネス用の Skype**です。
    
3. **電話会議**には、**ビジネス管理センターの Skype**、左側のナビゲーションでの > **Microsoft ブリッジ設定**します。
    
4. **会議参加の経験**をするには、[**ミーティングの入場を有効にして終了の通知をオンにする**というラベルの付いたチェック ボックスを参照してください。
    
  - **選択**会議に入る前に自分の名前を記録するための呼び出し元が求められます。 これがデフォルトで選択されます。
    
  - **クリア**呼び出し元はない会議に入る前に自分の名前を記録するよう求められます。
    
5. 変更を行ったら、[**保存**] をクリックします。
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757)コマンドレットを使用することができます。
    
-  Windows PowerShell は、ユーザーとは、ユーザーの許可を管理します。 Windows PowerShell を実行する複数のタスクがある場合、日常的な作業を簡素化する管理の単一ポイントを使用して Office 365 を管理できます。 Windows PowerShell を使い始めるには、以下のトピックを参照してください。
    
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

