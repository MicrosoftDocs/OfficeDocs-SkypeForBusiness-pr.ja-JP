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
ms.openlocfilehash: 4baa6f18e92eb284cce8610ba576b30dd6d2f320
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-lync-users-for-remote-call-control-in-lync-server-2013"></a>Lync Server 2013 で Lync ユーザーのリモート通話コントロールを有効にする

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-21_

サーバーベースのインバンドプロビジョニングポリシーを使用して、リモート通話コントロールの Lync ユーザーを構成することができます。 インバンドプロビジョニングの設定は、Lync Server コントロールパネルまたは Lync Server 管理シェルコマンドラインインターフェイスを使用して管理できます。 これらのツールは、以前のリリースでグループポリシー設定を管理するために使用された Windows Management Instrumentation (WMI) スナップインに代わるものです。

ユーザーが Lync で独自のリモート通話コントロールの設定を構成できるようにする場合は、 **Line SERVER uri**と**line uri**値を指定せずに、サーバー上のユーザーのリモート通話コントロール設定を構成できます。 適切な**回線サーバーの uri**と**回線 uri**の値をユーザーに伝えるようにして、これらの設定を構成するための指示をユーザーに提供してください。 Lync Server でリモート通話コントロールを手動で構成する手順については、Microsoft Office web サイトの<http://go.microsoft.com/fwlink/p/?linkid=210132> 「Lync クライアントドキュメント」の「電話のオプションと番号を設定する」を参照してください。

既存の Communications Server 2007 R2 または Communications Server 2007 の展開を使用している場合、Communicator 2007 R2 および Communicator 2007 クライアントは、side-by-side 移行時にグループポリシーを引き続き使用します。 ただし、ポリシー設定が Lync クライアントに引き継がれるようにするには、対応する Lync Server のインバンドプロビジョニング設定を構成する必要があります。

<div>


> [!NOTE]  
> ユーザーのリモート通話コントロールを有効にするには、ユーザーに行 URI と回線サーバー URI の両方を提供する必要があります。 「 <A href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 のリモート通話コントロールの展開タスク</A>」で説明されているように、これらの設定には、必ずゲートウェイで必要な構文を使用する必要があります。<BR>回線サーバー URI のドメインが、ゲートウェイへの静的ルートを構成する際に MatchUri パラメーターで指定した宛先ドメインと同じであることを確認してください。<BR>回線 URI は、"TEL:" プレフィックス (たとえば、tel: + 14255550150) を使用して、ユーザーに対して e.164 形式で割り当てられた電話番号を指定します。 内線番号を構成する場合は、tel: + 14255550150; ext = 111 の形式にします。 以前にユーザーの回線 URI を構成していて、値が変更されていない場合は、リモート通話コントロールに対してユーザーを有効にするときに、回線 URI を指定する必要はありません。



</div>

<div>

## <a name="to-enable-remote-call-control-for-lync-enabled-users-by-using-management-shell"></a>管理シェルを使用して、Lync で有効になっているユーザーのリモート通話コントロールを有効にするには

1.  Lync Server 管理シェルがインストールされているコンピューターに、RTCUniversalServerAdmins グループのメンバーとして、または、**設定-CsUser**コマンドレットを割り当てた役割ベースのアクセス制御の役割としてログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

3.  **Set-CsUser** コマンドレットを使用して、Lync で有効にされている既存のユーザーのリモート通話コントロールを構成するには、次の操作を行います。
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    次にその例を示します。
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

</div>

<div>

## <a name="to-configure-users-for-remote-call-control-by-using-lync-server-control-panel"></a>Lync Server コントロール パネルを使用して、リモート通話コントロールに対してユーザーを構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで **[ユーザー]** をクリックします。

4.  [**ユーザーの検索**] ボックスに、表示名、名、姓、セキュリティアカウントマネージャー (SAM) のアカウント名、SIP アドレス、または必要なユーザーアカウントの回線 Uri (Uniform resource identifier) の全体 (または最初の部分) を入力し、[**検索**] をクリックします。

5.  表中の変更するユーザー アカウントをクリックします。

6.  **[編集]** メニューの **[変更]** をクリックします。

7.  **[テレフォニー]** で、次のいずれかの操作を実行します。
    
      - リモート通話コントロールを有効にして、ユーザーが Lync 2013 から自社の構内交換機 (PBX) 電話を制御できるようにして、PC 間の音声通話と PC 間通話を行うには、[**リモート通話コントロール**] をクリックします。 **[回線 URI]** でユーザーの電話番号を指定します。 **[回線サーバー URI]** で、SIP/CSTA ゲートウェイの SIP URI を指定します。
    
      - リモート通話コントロールを有効にするが、PC 間の音声通話を無効にし、ユーザーのみが Lync 2013 からの PBX 電話を制御できるようにするには、[**リモート通話コントロールのみ**] をクリックします。 **[回線 URI]** でユーザーの電話番号を指定します。 **[回線サーバー URI]** で、SIP/CSTA ゲートウェイの SIP URI を指定します。

8.  終了したら、**[確定]** をクリックします。

</div>

</div>

<span> </span>

</div>

</div>

</div>

