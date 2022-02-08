---
title: 会議への参加を管理し、会議のアナウンスをSkype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: 会議への参加を管理し、会議にアナウンスを残す方法についてSkype for Business Server。'
ms.openlocfilehash: ac259999daaa2fed0988e59d9ab40b9370a2fba8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62385785"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>会議への参加を管理し、会議のアナウンスをSkype for Business Server
 
**概要:** 会議への参加を管理し、会議に参加してアナウンスを残す方法については、Skype for Business Server。
  
ダイヤルイン ユーザーが会議に参加または退出すると、会議アナウンス アプリケーショントーンを再生するか、名前を言って、入退場をアナウンスできます。 次のパラメーターを使用して、Skype for Business Server管理シェルおよび **Set-CsDialinConferencing** コマンドレットを使用して、アナウンスの動作を変更できます。
  
- EnableNameRecording - 匿名の参加者が会議に参加する前に自分の名前を記録するかどうかを指定します。 既定値は "$true" で、匿名の参加者は会議に参加するときに名前を入力するように求めるメッセージが表示されます。 (認証された参加者は、表示名が代わりに使用されるので、自分の名前は記録されません)。
    
- EntryExitAnnouncementsEnabledByDefault - アナウンスが既定でオンまたはオフになっているかどうかを示します。 既定値は "$false" で、参加者が会議に参加または退会するときに、既定ではアナウンスはありません。 会議の開催者は、会議をスケジュールするときにこの設定を上書きできます。
    
- EntryExitAnnouncementsType - 参加者が会議に参加または会議を離れるたびに実行されるアクションを示します。アナウンスが有効になります。 既定値は "UseNames" です。これは、アナウンスがオンになっているときに"Ken Myer が会議に参加しました" のようなアナウンスが発生します。
    
これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. 管理シェルをSkype for Business Serverする **: [スタート**] をクリックし、[すべてのプログラム] をクリックし、[**2015** 年Skype for Business] をクリックし、[管理シェルSkype for Business Server **クリックします**。
    
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

構文やパラメーターの完全なリストなど、詳細については、「 [Set-CsDialInConferencingConfiguration」を参照してください](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
