---
title: 'Lync Server 2013: 会議の構成設定を表示する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で会議の構成設定を表示する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Server 2013 コントロールパネルで、会議の構成設定を使用して、展開での会議の実装方法を制御します。 これには、次の会議の設定が含まれます。

  - Lync Server 2013 を展開するときに既定で作成されるグローバル構成。

  - 特定のサイトまたはユーザーに対して会議を実装する方法を指定するために作成および使用できる、オプションのサイトレベルとユーザーレベルの構成。

<div>

## <a name="to-view-meeting-configuration-settings"></a>会議の構成設定を表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**会議**] をクリックし、[**会議の設定**] をクリックします。

4.  [**会議の構成**] ページで、表示する会議構成をクリックします。

5.  [**ファイルフィルターの編集**] で、[**詳細の表示**] を選択します。 チェックボックスをオンにします。
    
    [**会議の構成\<の\>編集]-** 選択したポリシーの設定が表示されたポリシーが開きます。 設定の構成の詳細については、「 [Lync Server 2013 で会議構成設定のコレクションを作成または変更する](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)」を参照してください。

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して会議の構成情報を表示する

会議の構成設定を表示するには、Windows PowerShell と、「Csmeeting 構成」コマンドレットを使用します。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-meeting-configuration-information"></a>会議の構成情報を表示するには

  - すべての会議の構成設定に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
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

詳細については、「 [Cs会議構成](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration)コマンドレットのヘルプ」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

