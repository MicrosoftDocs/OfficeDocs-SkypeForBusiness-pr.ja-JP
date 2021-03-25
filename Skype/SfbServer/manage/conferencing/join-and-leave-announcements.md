---
title: Skype for Business Server で会議への参加と退出のお知らせを管理する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: Skype for Business Server で会議への参加とアナウンスを管理する方法について学習します。'
ms.openlocfilehash: 796266dd3b571e525f657d5dbe712d1577779cae
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119456"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Skype for Business Server で会議への参加と退出のお知らせを管理する
 
**概要:** Skype for Business Server で会議への参加とアナウンスを残す方法について学習します。
  
ダイヤルイン ユーザーが会議に参加または退出する場合、会議アナウンス アプリケーションは、トーンを再生するか、名前を言って、自分の入り口または退出をアナウンスできます。 次のパラメーターを使用して、Skype for Business Server 管理シェルと **Set-CsDialinConferencing** コマンドレットを使用して、アナウンスの動作を変更できます。
  
- EnableNameRecording - 匿名の参加者が会議に参加する前に自分の名前を記録するかどうかを指定します。 既定値は "$true" で、匿名の参加者は会議に参加するときに名前を入力するように求めるメッセージが表示されます。 (認証された参加者は、表示名が代わりに使用されるので、自分の名前は記録されません)。
    
- EntryExitAnnouncementsEnabledByDefault - アナウンスが既定でオンまたはオフになっているかどうかを示します。 既定値は "$false" で、参加者が会議に参加または退会するときに、既定ではアナウンスはありません。 会議の開催者は、会議をスケジュールするときにこの設定を上書きできます。
    
- EntryExitAnnouncementsType - 参加者が会議に参加または会議を離れるたびに実行されるアクションを示します。アナウンスが有効になります。 既定値は "UseNames" です。これは、アナウンスがオンになっているときに"Ken Myer が会議に参加しました" のようなアナウンスが発生します。
    
これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを開始する: **[スタート**] をクリックし、[すべてのプログラム] をクリックし **、[Skype for Business 2015]** をクリックし、[Skype for Business Server 管理シェル]**をクリックします**。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

このコマンドレットは、会議に参加するときに参加者が自分の名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加または退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。
    
4. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

次の例では、Redmond のサイト スコープで設定が構成されています。 アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。 参加者が会議に参加または退出すると、トーンが再生されます。
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

構文やパラメーターの完全なリストを含む詳細については [、「Set-CsDialInConferencingConfiguration」を参照してください](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
