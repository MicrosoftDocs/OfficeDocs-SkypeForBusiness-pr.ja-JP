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
description: 'Skype for Business 管理センターを使用して、Skype for Business Online 会議で、エントリと退出のお知らせを有効または無効にする方法を説明します。 '
ms.openlocfilehash: 874624c3d7cfb184f4206f61cf2a91a67eb2e2cd
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779037"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-skype-for-business-online"></a>Skype for Business Online で会議のエントリと退出のお知らせを有効または無効にする

> [!Note]
> Microsoft Teams でのエントリと退出のお知らせについては、「[Microsoft Teams でエントリと退出のお知らせを有効または無効にする](/MicrosoftTeams/turn-on-or-off-entry-and-exit-announcements-for-meetings-in-teams)」を参照してください。

Office 365 で電話会議を設定する場合、電話会議ブリッジが表示されます。 会議ブリッジには、ユーザーが Skype for Business 会議にコールインするのに使用する 1 つ以上の電話番号を含めることができます。 
  
会議ブリッジは、電話機を使用して会議にダイヤルインしようとしているユーザーの呼び出しに答えます。 会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。 Skype for Business 会議の開催者には PIN が付与され、呼び出し元が Skype for Business アプリを使用して会議を開始できない場合は、その PIN を使用して会議を開始させることができます。 ただし、会議を開始するのに PIN が必要ないように設定をすることもできます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>会議の参加オプションの設定
    
1. **Skype for Business 管理センター**の左側にあるナビゲーションで、[**電話会議**]  >  [**Microsoft ブリッジ設定**] の順に開きます。
    
2. [ **会議参加のエクスペリエンス**] の下にある[**会議のエントリと退出の通知を有効にする**] を選択するかクリアします。 既定ではこれはすでに選択されています。 クリアすると、すでに会議に参加しているユーザーには、他のユーザーが会議にエントリ、または会議から退出した場合でも通知がされなくなります。
    
3. [**エントリ/退出のお知らせの種類**] の下にある [**名前または電話番号**] または [**トーン**] を選択します。
    
4. [**会議に参加する前に名前を記録するように参加者に依頼する**] をオンまたはオフにします。
    
5. 変更したら [**保存**] をクリックします。
    

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Windows PowerShell で管理する方法

- 時間を節約したり、自動化したりするには、[Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/en-us/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) コマンドレットを使用できます。
    
-  Windows PowerShell の場合、Skype for Business Online はユーザーの管理と、ユーザーが許可されている操作や許可されていない操作の管理に使います。Windows PowerShell により、単一の管理ポイントを使って Office 365 を管理でき、複数の作業を実行する必要があるときに日常業務を合理化できます。Windows PowerShell を使い始めるには、次のトピックを参照してください。
    
  - [Windows PowerShell を使用しなければならない理由](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell には、一度に多くのユーザー向けの設定変更をする場合など、速度、簡単さ、生産性の面で Office 365 管理センターだけを使用するよりも多くの利点があります。 次のトピックで、これらの利点を説明します。 
    
  - [Windows PowerShell と Skype for Business Online の概要](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Windows PowerShell による Skype for Business Online の管理](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [クイック リファレンス: Windows PowerShell を使用した一般的な Lync Online の管理タスクの実行](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > Windows PowerShell を使用した一般的な Skype for Business Online の管理タスクの実行[](https://go.microsoft.com/fwlink/?LinkId=294688)
  
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](/MicrosoftTeams/audio-conferencing-common-questions)
