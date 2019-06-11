---
title: 'Lync Server 2013: PSTN 使用状況レコードの表示'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View PSTN usage records
ms:assetid: 65025c78-c263-472c-9ff9-e170588f10b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398458(v=OCS.15)
ms:contentKeyID: 48184361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9042eca0b8ddd1f04b34c3fea0b57dd6235b69c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848197"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pstn-usage-records-in-lync-server-2013"></a>Lync Server 2013 での PSTN 使用状況レコードの表示

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-22_

公衆交換電話網 (PSTN) 利用状況レコードは、組織内のさまざまなユーザーまたはユーザーグループによって作成される通話のクラス (内部、ローカル、または長距離など) を指定します。 詳細については、計画ドキュメントの「 [Lync Server 2013 の PSTN 使用状況レコード](lync-server-2013-pstn-usage-records.md)」を参照してください。

<div>

## <a name="to-view-a-pstn-usage-record-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用して PSTN 使用状況レコードを表示するには

1.  RTCUniversalServerAdmins グループのメンバーとして、あるいは CsVoiceAdministrator、CsServerAdministrator、または CsAdministrator の役割のメンバーとしてコンピューターにログオンします。 詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**音声ルーティング**] をクリックし、[**PSTN 使用法**] をクリックします。

4.  [**PSTN 使用法**] ページで、表示する PSTN 使用法レコードを選択状態にし、[**編集**] をクリックして、[**詳細の表示**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > 選択した PSTN 使用法レコードの読み取り専用ページに、関連付けられたルートと関連付けられた音声ポリシーが表示されます。

    
    </div>

</div>

<div>

## <a name="viewing-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した PSTN 使用状況情報の表示

Windows PowerShell と**Get-CsPstnUsage**コマンドレットを使用して、PSTN の使用状況を表示することもできます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-view-pstn-usage-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して PSTN の使用状況の情報を表示するには

  - すべての PSTN 使用状況に関する情報を表示するには、Lync Server 管理シェルで次のコマンドを入力し、enter キーを押します。
    
        Get-CsPstnUsage
    
    このコマンドは、次のような情報を返します。
    
        Identity : Global
        Usage    : {Internal, Local, Long Distance}

</div>

詳細については、「 [Get-CsPstnUsage](https://docs.microsoft.com/powershell/module/skype/Get-CsPstnUsage)」をご覧ください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で音声ポリシーを作成し、PSTN 使用状況レコードを構成する](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Lync Server 2013 で音声ポリシーを変更し、PSTN 使用状況レコードを構成する](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

