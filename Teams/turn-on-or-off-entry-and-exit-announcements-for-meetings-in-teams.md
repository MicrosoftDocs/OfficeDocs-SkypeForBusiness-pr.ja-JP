---
title: Microsoft Teams で会議の入退室通知をオンまたはオフにする
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Microsoft Teams の会議の入退室通知をオンまたはオフにする方法について説明します。 '
ms.openlocfilehash: a646718d861737435244ee43c7206402f602f63c
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/25/2018
ms.locfileid: "25012458"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Microsoft Teams で会議の入退室通知をオンまたはオフにする

Office 365 の電話会議をセットアップしている場合、電話会議ブリッジを取得します。 電話会議ブリッジには、ユーザーが Microsoft Teams の会議にダイヤルインするために使用する 1 つまたは複数の電話番号を含めることができます。 
  
電話会議ブリッジは、電話機を使用して会議にダイヤルインしているユーザーの通話に応答します。 会議ブリッジは、まず会議の自動応答の音声プロンプトで呼び出し元に応答します。設定によっては、次に通知を再生、呼び出し元に名前を記録するよう依頼し、PIN セキュリティをセットアップします。 PIN は Microsoft Teams の会議の開催者に付与され、Microsoft Teams アプリを使用して会議を開始することができない場合に、PIN で会議を開始することができます。 ただし、会議を開始するのに PIN を必要としないように設定することができます。

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>会議参加のオプションを設定する

1. 左側のナビゲーションで、[**会議**]  >  [**会議ブリッジ**] に移動します。 

2. [**会議ブリッジ**] ページの最上部で、[**ブリッジの設定**] をクリックします。 

3. [**ブリッジ設定**] ウィンドウで、[**会議の開始と終了の通知**] を有効または無効にします。 これは既定では選択されています。 この選択をクリアすると、既に参加済みのユーザーは、誰かが入ってきたり退出したりしたときに通知を受け取りません。
    
4. [**開始/終了のお知らせの種類**] で、[**名前または電話番号**] または [**トーン**] を選択します。
    
5. [**名前または電話番号**] を選ぶ場合は、[**発信者に、会議に参加する前に自分の名前を記録するように要求します**] を有効または無効にします。
    
6. [**保存**] をクリックします。

## <a name="want-to-know-more-about-windows-powershell"></a>Windows PowerShell の詳細情報

Windows PowerShell は、ユーザーと、ユーザーに許可されていることと許可されていないことを管理するためにあるということです。Windows PowerShell があれば、一元管理を使用して Office 365 を管理し、複数のタスクを抱えているときに、日常の仕事を簡素化することができます。Windows PowerShell を開始するには、これらのトピックを参照してください。
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Windows PowerShell で Office 365 を管理するための最善の方法](https://go.microsoft.com/fwlink/?LinkId=525142)
    
Windows PowerShell の詳細については、「[Microsoft Teams PowerShell のリファレンス](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)」をご覧ください。
  
## <a name="related-topics"></a>関連トピック

[電話会議に関するよくある質問](audio-conferencing-common-questions.md)
