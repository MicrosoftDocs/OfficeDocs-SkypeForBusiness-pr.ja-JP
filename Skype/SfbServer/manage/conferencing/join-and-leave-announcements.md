---
title: 会議の参加を管理し、お知らせの Skype ビジネス サーバーのままに
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: '概要: は、会議の参加を管理し、お知らせの Skype ビジネス サーバーのままにする方法を説明します。'
ms.openlocfilehash: ace07fdc3325d97e443297265892e7bcc4bce562
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919522"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a>会議の参加を管理し、お知らせの Skype ビジネス サーバーのままに
 
**の概要:** 会議の参加を管理し、お知らせの Skype ビジネス サーバーのままにする方法を説明します。
  
ダイヤルイン ユーザーは、参加または会議のままにして、会議アナウンス アプリケーションの開始を発表したり、音を再生するか、名前を言うまでに終了します。 Skype ビジネス サーバー管理シェルは、次のパラメーターを使用して**セット CsDialinConferencing**コマンドレットを使用して、お知らせがどのように動作を変更できます。
  
- EnableNameRecording - 会議に出席する前に名前を記録するよう匿名参加者に依頼するかどうかを指定します。既定値は "$true" で、これは、会議に出席するときに名前を言うように匿名参加者に求めることを意味します (認証された参加者の場合は、表示名が代わりに使用されるため、名前を記録しません)。
    
- EntryExitAnnouncementsEnabledByDefault - 既定でアナウンス機能をオンまたはオフにするかどうかを示します。既定値は "$false" で、これは既定で、参加者が会議に出席または会議から退席するときにアナウンスが行われないことを意味します。ミーティング開催者は、ミーティングをスケジュールするときにこの設定を上書きできます。
    
- EntryExitAnnouncementsType - アナウンスが有効な会議に参加者が出席または退席するときに実行されるアクションを示します。既定値は "UseNames" で、これは、アナウンスをオンにすると、"Ken Myer が会議に参加しました" というようなアナウンスが行われることを意味します。
    
これらの設定は、グローバル スコープまたはサイト スコープで構成できます。サイト スコープで構成した設定は、グローバル スコープで構成した設定より優先されます。
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>会議への出退席のアナウンス方法を変更するには

1. コンピューターに RTCUniversalServerAdmins グループのメンバーとしてログオンするか、Cs-ServerAdministrator または CsAdministrator 役割のメンバーとしてログオンします。
    
2. Skype for Business Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Skype for Business 2015**]、[**Skype for Business Server 管理シェル**] の順にクリックします。
    
3. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Get-CsDialinConferencingConfiguration
   ```

このコマンドレットでは、参加者が会議に参加するときに自分の名前を記録する必要がかどうかと、参加者の参加またはダイヤルイン会議のままにするときの Skype ビジネス サーバーの応答に関する情報を取得します。
    
4. コマンド プロンプトで次のコマンドを実行します。
    
   ```
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

次の例では、設定が Redmond のサイト スコープで定義されます。アナウンスはオンにされますが、会議に参加するときに名前を言うように参加者が求められることはありません。参加者が会議に出席または会議から退席するときには、トーン音が再生されます。
  
```
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

詳細については、構文やパラメーターの完全なリストを含む[セット CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps)を参照してください。
  

