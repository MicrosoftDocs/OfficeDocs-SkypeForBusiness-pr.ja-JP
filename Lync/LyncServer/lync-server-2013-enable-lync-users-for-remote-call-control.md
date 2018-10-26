---
title: 'Lync Server 2013: リモート通話コントロールの Lync ユーザーの有効化'
TOCTitle: リモート通話コントロールの Lync ユーザーの有効化
ms:assetid: f39bc10d-034c-4875-a0b8-554e1109e7e6
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg615048(v=OCS.15)
ms:contentKeyID: 48274112
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 でのリモート通話コントロールの Lync ユーザーの有効化

 

_**トピックの最終更新日:** 2016-12-08_

サーバーベースのインバンド プロビジョニング ポリシーを使用して、 Lync ユーザーを構成し、リモート通話コントロールに対応させることができます。インバンド プロビジョニングの設定は、 Lync Server コントロール パネルまたは Lync Server 管理シェル コマンド ライン インターフェイスを使用して管理できます。これらのツールは、以前のリリースでグループ ポリシー設定の管理に使用していた Windows Management Instrumentation (WMI) スナップインに代わる機能です。

ユーザーが Lync で自分のリモート通話コントロールの設定を構成できるようにする場合は、サーバーでのユーザーのリモート通話コントロール設定を、\[**回線サーバー URI**\] や \[**回線 URI**\] の値を指定しないで構成することができます。該当する \[**回線サーバー URI**\] および \[**回線 URI**\] の値をユーザーに通知して、これらの設定の構成手順を説明してください。 Lync Server でのリモート通話コントロールの手動での構成手順については、「電話オプションと番号の設定」( [http://go.microsoft.com/fwlink/p/?linkid=210132](http://go.microsoft.com/fwlink/p/?linkid=210132%26clcid=0x411)) を参照してください (Microsoft Office Web サイトの Lync クライアント ドキュメントにあります)。

既存の Communications Server 2007 R2 または Communications Server 2007 展開がある場合、 Communicator 2007 R2 および Communicator 2007 クライアントはサイド バイ サイド移行中もグループ ポリシーを使用し続けます。ただし、ポリシー設定を Lync クライアントに移す場合は、同等の Lync Server インバンド プロビジョニング設定を構成する必要があります。

> [!NOTE]  
> リモート通話コントロールに対してユーザーを有効にするには、ユーザーに回線 URI と回線サーバー URI の両方を提供する必要があります。「<a href="lync-server-2013-deployment-tasks-for-remote-call-control.md">Lync Server 2013 のリモート通話コントロールの展開タスク</a>」で説明するように、これらの設定については、必ず、ゲートウェイが要求する構文を使用する必要があります。<br />
> 回線サーバー URI のドメインが、ゲートウェイへの静的ルートを構成する際に MatchUri パラメーターで指定した宛先ドメインと一致することを確認してください。<br />
> 回線 URI は、ユーザーに割り当てられる電話番号を、&quot;TEL:&quot; というプレフィックスを付けて E.164 形式で指定します (たとえば、tel:+14255550150)。内線番号を構成する場合は、形式は tel:+14255550150;ext=111 のようになります。ユーザーの回線 URI が構成済みで値が変更されていない場合は、リモート通話コントロールに対してユーザーを有効にする際に、回線 URI を指定する必要はありません。


## 管理シェルを使用して、Lync で有効になっているユーザーのリモート通話コントロールを有効にするには

1.  RTCUniversalServerAdmins グループまたは、 **Set-CsUser** コマンドレットを割り当てた役割ベースのアクセス制御の役割のメンバーとして、 Lync Server 管理シェルがインストールされているコンピューターにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  **Set-CsUser** コマンドレットを使用して、Lync で有効にされている既存のユーザーのリモート通話コントロールを構成するには、次の操作を行います。
    
        Set-CsUser -Identity <User ID> -EnterpriseVoiceEnabled $false -LineServerUri <SIP URI of the SIP/CSTA gateway> -LineUri <TEL URI of the user> -RemoteCallControlTelephonyEnabled $true
    
    次に例を示します。
    
        Set-CsUser -Identity "Katie Jordan" -EnterpriseVoiceEnabled $false -LineServerUri sip:rccgateway@contoso.net -LineUri tel:+14255550150 -RemoteCallControlTelephonyEnabled $true

## Lync Server コントロール パネルを使用して、リモート通話コントロールに対してユーザーを構成するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**ユーザー**\] をクリックします。

4.  \[**ユーザーの検索**\] ボックスに、検索するユーザー アカウントの表示名、名、姓、セキュリティ アカウント マネージャー (SAM) のアカウント名、SIP アドレス、または回線 URI (Uniform Resource Identifier) の全部または最初の一部を入力して、\[**検索**\] をクリックします。

5.  表中の変更するユーザー アカウントをクリックします。

6.  \[**編集**\] メニューの \[**変更**\] をクリックします。

7.  \[**テレフォニー**\] で、次のいずれかの操作を実行します。
    
      - ユーザーが Lync 2013 から自分の構内交換機 (PBX) 電話を制御して PC 間の音声通話および PC と電話間通話を行うことができるようにするリモート通話コントロールを有効にするには、\[**リモート通話コントロール**\] をクリックします。\[**回線 URI**\] でユーザーの電話番号を指定します。\[**回線サーバー URI**\] で、SIP/CSTA ゲートウェイの SIP URI を指定します。
    
      - リモート通話コントロールは有効にするが、PC 間の音声通話は無効にし、ユーザーが Lync 2013 から自分の PBX 電話を制御して PC と電話間の通話を行うことだけを可能にするには、\[**リモート通話コントロールのみ**\] をクリックします。\[**回線 URI**\] でユーザーの電話番号を指定します。\[**回線サーバー URI**\] で、SIP/CSTA ゲートウェイの SIP URI を指定します。

8.  終了したら、\[**確定**\] をクリックします。

