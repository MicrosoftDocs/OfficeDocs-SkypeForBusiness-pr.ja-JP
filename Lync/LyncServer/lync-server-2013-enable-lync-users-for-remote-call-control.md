---
title: 'Lync Server 2013: リモート通話コントロールの Lync ユーザーの有効化'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Lync users for remote call control
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48185795
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 260cfc2d3a0b185d58e90f4944162ea23135a0b9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736237"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 でのリモート通話コントロールの Lync ユーザーの有効化

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-21_

サーバーベースのインバンドプロビジョニングポリシーを使用して、リモート通話コントロールの Lync ユーザーを構成することができます。 Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドラインインターフェイスを使用して、インバンドプロビジョニングの設定を管理できます。 これらのツールは、以前のリリースでグループポリシー設定を管理するために使用された Windows Management Instrumentation (WMI) スナップインと置き換わります。

ユーザーが Lync で独自のリモート通話コントロールの設定を構成できるようにする場合は、サーバー上のユーザーに対してリモート通話コントロールの設定を構成できます。これには、 **Line SERVER uri**と**ライン URI**の値を指定する必要がありません。 適切な**行サーバーの uri**と**行の uri**の値をユーザーに伝え、これらの設定を構成するための手順をユーザーに提供してください。 Lync Server のリモート通話コントロールを手動で構成する手順については、Microsoft Office web サイトの<http://go.microsoft.com/fwlink/p/?linkid=210132> Lync クライアントドキュメントの「電話のオプションと番号を設定する」を参照してください。

既存の通信サーバー 2007 R2 または Communications Server 2007 の展開がある場合、Communicator 2007 R2 および Communicator 2007 クライアントは、並列での移行中にグループポリシーを引き続き使用します。 ただし、ポリシー設定が Lync クライアントに引き継がれるようにするには、対応する Lync Server のインバンドプロビジョニングの設定を構成する必要があります。

<div>


> [!NOTE]  
> ユーザーに対してリモート呼び出しの制御を有効にするには、行の URI と Line Server の URI の両方をユーザーに提供する必要があります。 「 <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 のリモート通話コントロールの展開タスク</A>」で説明したように、これらの設定には、ゲートウェイで必要な構文を使用する必要があります。<BR>Line Server URI のドメインは、ゲートウェイへの静的ルートを構成するときに MatchUri パラメーターで指定した宛先ドメインと同じであることを確認してください。<BR>[Line URI] は、ユーザーに割り当てられた電話番号を164形式で指定します (例: tel: + 14255550150)。 内線番号を構成する場合は、"tel: + 14255550150; ext = 111" の形式になります。 以前にユーザーの行の URI を構成していて、その値が変更されていない場合は、リモート呼び出しの制御のためにユーザーを有効にするときに、行の URI を指定する必要はありません。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>管理シェルを使用して Lync 対応ユーザーのリモート通話コントロールを有効にするには

1.  Lync Server 管理シェルが RTCUniversalServerAdmins グループのメンバーとして、または、**ユーザー設定のユーザー**コマンドレットを割り当てられた役割ベースのアクセス制御の役割としてインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

3.  **Set-csuser**コマンドレットを使用して、既存の Lync 対応ユーザーのリモート通話コントロールを構成するには、次の操作を行います。
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    次に例を示します。
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Lync Server コントロールパネルを使用してリモート通話コントロールのユーザーを構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーション バーで [**ユーザー**] をクリックします。

4.  [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) アカウント名、SIP アドレス、または必要なユーザーアカウントの行の Uniform resource IDENTIFIER (URI) のすべて (または最初の部分) を入力し、[**検索**] をクリックします。

5.  表で、変更するユーザーアカウントをクリックします。

6.  [**編集**] メニューの [**変更**] をクリックします。

7.  [**テレフォニー**] で、次のいずれかの操作を行います。
    
      - リモート通話コントロールを有効にして、ユーザーが自分のプライベートブランチ exchange (PBX) 電話を Lync 2013 から制御できるようにするには、[**リモート通話コントロール**] をクリックします。 [**行の URI**] で、ユーザーの電話番号を指定します。 [ **Line SERVER URI**] で、SIP/csta ゲートウェイの sip URI を指定します。
    
      - リモート通話コントロールを有効にして、PC 間の音声通話を無効にし、ユーザーだけが Lync 2013 から自分の PBX 電話を制御できるようにするには、[**リモート通話の制御のみ**] をクリックします。 [**行の URI**] で、ユーザーの電話番号を指定します。 [ **Line SERVER URI**] で、SIP/csta ゲートウェイの sip URI を指定します。

8.  完了したら、[**コミット**] をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

