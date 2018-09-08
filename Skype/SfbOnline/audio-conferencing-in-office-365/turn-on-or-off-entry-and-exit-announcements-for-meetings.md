---
title: Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Skype for Business 管理センターを使用して、Skype for Business Online 会議で、エントリと退出のお知らせを有効または無効にする方法を説明します。 '
ms.openlocfilehash: b00c52d905fb031c7f0eaebc57f9fbb88549daa0
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23884062"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする

> [!Note]
> Microsoft Teams でのエントリと退出のお知らせについては、「[Microsoft Teams でエントリと退出のお知らせを有効または無効にする](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)」を参照してください。

Office 365 で電話会議を設定する場合、電話会議ブリッジが表示されます。 会議ブリッジには、ユーザーが Skype for Business 会議にコールインするのに使用する 1 つ以上の電話番号を含めることができます。 
  
会議ブリッジは、電話機を使用して会議にダイヤルインしようとしているユーザーの呼び出しに答えます。 会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。 Skype for Business 会議の開催者には PIN が付与され、呼び出し元が Skype for Business アプリを使用して会議を開始できない場合は、その PIN を使用して会議を開始させることができます。 ただし、会議を開始するのに PIN が必要ないように設定をすることもできます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>会議の参加オプションの設定
    
1. 既定値は 5 です。******** > ****
    
2. **会議参加の経験**をするには、[をオンまたはオフの**ミーティングのエントリを有効にしてオンにする通知を終了**します。 既定ではこれはすでに選択されています。 場合はこのオプションをオフにすると、データを入力したり、会議を離れると、会議に参加しているユーザーが通知されません。
    
3. [**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。
    
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
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>このモジュールは、64 ビットのコンピューターでのみサポートされ、Microsoft ダウンロード センターの「Skype for Business Online 用 Windows PowerShell モジュール」からダウンロードできます。

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
