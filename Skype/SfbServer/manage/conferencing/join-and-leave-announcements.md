---
title: Skype for Business Server で会議への参加および退出のアナウンスを管理する
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
description: '概要: Skype for Business Server で会議への参加および退出のアナウンスを管理する方法について学習します。'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828107"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>Skype for Business Server で会議への参加および退出のアナウンスを管理する
 
**概要:** Skype for Business Server で会議への参加および退出のアナウンスを管理する方法について学習します。
  
ダイヤルイン ユーザーが会議に参加または会議から退出すると、会議アナウンス アプリケーションは、トーンを再生するか、名前を言って、開始または退出をアナウンスできます。 Skype for Business Server 管理シェルおよび **Set-CsDialinConferencing** コマンドレットを使用して、次のパラメーターを使用して、アナウンスの動作を変更できます。
  
- EnableNameRecording - 会議に参加する前に、匿名の参加者に名前の記録を求めるかどうかを決定します。 既定値は "$true" で、匿名の参加者は会議に参加するときに名前を入力するように求めるメッセージが表示されます。 (認証された参加者は、表示名が代わりに使用されるので、名前は記録されません)。
    
- EntryExitAnnouncementsEnabledByDefault - アナウンスが既定でオンまたはオフになっているかどうかを示します。 既定値は "$false" です。これは、参加者が会議に参加または会議から退出するときにアナウンスが既定で行えなを意味します。 会議の開催者は、会議のスケジュール時にこの設定を上書きできます。
    
- EntryExitAnnouncementsType - アナウンスが有効になっている会議に参加者が参加または会議から離れるたびに実行されるアクションを示します。 既定値は "UseNames" です。これは、アナウンスがオンになっているときに"Ken Myer が会議に参加しました" のようなアナウンスが表示されるという意味です。
    
これらの設定は、グローバル スコープまたはサイト スコープで構成できます。 サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1. RTCUniversalServerAdmins グループのメンバーか、Cs-ServerAdministrator または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。
    
2. Skype for Business Server 管理シェルを起動します。[スタート] ボタン、[すべてのプログラム] の順にクリックし **、[Skype for Business 2015]** をクリックして **、[Skype for Business Server 管理** シェル] をクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

このコマンドレットは、参加者が会議に参加するときに名前を記録する必要があるかどうか、および参加者がダイヤルイン会議に参加またはダイヤルイン会議から退出するときに Skype for Business Server がどのように応答するかに関する情報を取得します。
    
4. コマンド プロンプトで次のコマンドを実行します。
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

次の例では、Redmond のサイト スコープで設定を構成します。 アナウンスはオンにされますが、会議に参加するときに名前を言うよう参加者が求められることはありません。 参加者が会議に参加または会議から退出すると、トーンが再生されます。
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

構文やパラメーターの完全な一覧など、詳細については [、「Set-CsDialInConferencingConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)。
  

