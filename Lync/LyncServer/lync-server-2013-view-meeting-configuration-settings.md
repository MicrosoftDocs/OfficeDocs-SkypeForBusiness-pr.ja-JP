---
title: 'Lync Server 2013: 会議の構成設定の表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9ad61f93cd7c65be04d30cf35638019ddc7ee58
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506334"
---
# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で会議の構成設定を表示する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルでは、会議の構成設定を使用して、展開での会議の実装方法を制御します。 これには、次の会議構成が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはユーザーに対する会議の実装方法を指定するために作成して使用できるオプションのサイトレベルおよびユーザーレベルの構成。

<div>

## <a name="to-view-meeting-configuration-settings"></a>会議構成設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで、[**会議**] をクリックし、[**会議の構成**] をクリックします。

4.  [**会議の構成**] ページで、表示する会議構成をクリックします。

5.  [**ファイル フィルターの編集**] で、[**詳細の表示**] チェック ボックスをオンにします。
    
    **会議の構成の \<policy\> 編集-** 選択したポリシーの設定を表示して開きます。 設定の構成の詳細については、「 [Lync Server 2013 の会議構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)」を参照してください。

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して会議構成情報を表示する

会議の構成設定は、Windows PowerShell と Get-CsMeetingConfiguration コマンドレットを使用して表示できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-view-meeting-configuration-information"></a>会議の構成情報を表示するには

  - すべての会議構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、ENTER キーを押します。
    
        Get-CsMeetingConfiguration
    
    次のような情報が表示されます。
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

</div>

詳細については、「 [get-help の構成](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) 」のコマンドレットのヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

