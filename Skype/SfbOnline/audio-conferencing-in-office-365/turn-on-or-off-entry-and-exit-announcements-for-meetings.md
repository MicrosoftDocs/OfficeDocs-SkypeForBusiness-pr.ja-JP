---
title: エントリ無効を切り替えるし、Skype でのオンライン ビジネスの会議のお知らせを終了します。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'エントリを有効にして、Skype、Skype を使用するビジネス管理センターのオンライン ビジネスの会議のためにアナウンスをオンまたはオフを終了する方法について説明します。 '
ms.openlocfilehash: d6d1b70713ac0cd7a38f7de9cb84f0acb54cbe30
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490487"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>エントリ無効を切り替えるし、Skype でのオンライン ビジネスの会議のお知らせを終了します。

> [!Note]
> マイクロソフトのチームでの開始と終了のお知らせについては、[マイクロソフトのチームでの会議の開始と終了のお知らせを切り替えるには、有効にする](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)を参照してください。

Office 365 に電話会議を設定する場合、オーディオ会議ブリッジが表示されます。 会議用ブリッジは、ビジネス会議のため、Skype へのコールを使用する 1 つまたは複数の電話番号を含めることができます。 
  
会議用ブリッジの電話を使用して会議にダイヤルインするユーザーが呼び出しに応答します。 会議用ブリッジ会議自動アテンダントからの音声メッセージを呼び出し元に応答しの設定によってことができます再生の通知は、呼び出し元が自分の名前を記録し、暗証番号 (pin) のセキュリティを設定するに問い合わせてください。 Skype をビジネス会議の開催者に、暗証番号 (pin) が与えられ、ビジネス アプリケーションに、Skype を使用してミーティングを開始することはできない場合は、会議を開始することができます。 できます、ただし、ように設定すると、暗証番号 (pin) が会議を開始する必要はありません。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>ミーティングの参加オプションの設定
    
1. 既定値は 5 です。
    
2. **会議参加の経験**をするには、[をオンまたはオフの**ミーティングのエントリを有効にしてオンにする通知を終了**します。 これがデフォルトで選択されます。 場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知されません。
    
3. [**開始/終了のお知らせの種類****名前や電話番号**」または「**トーン**を選択します。
    
4. 確認するか、**ミーティングに参加する前に自分の名前を記録するための呼び出し元の確認**をオフにします。
    
5. 変更したら [ **保存**] をクリックします。
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を短縮または、これを自動化するには、[セット CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)コマンドレットを使用することができます。
    
-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、実行しようとする設定の変更多くのユーザーを一度に 1 つなどの Office 365 管理センターを使用するだけでスピード、シンプルさと生産性に多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
