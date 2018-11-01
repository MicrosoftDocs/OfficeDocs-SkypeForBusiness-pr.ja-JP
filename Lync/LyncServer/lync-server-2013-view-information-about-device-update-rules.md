---
title: デバイス更新ルールに関する情報の表示
TOCTitle: デバイス更新ルールに関する情報の表示
ms:assetid: d6677ca4-024b-4816-8511-8d7630788107
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ994077(v=OCS.15)
ms:contentKeyID: 52056717
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# デバイス更新ルールに関する情報の表示

 

_**トピックの最終更新日:** 2013-02-23_

既にインポートしたデバイス更新ルールの詳細 (更新プログラムが適用されるデバイスの種類、モデル、ブランド、更新プログラムのバージョンと種類、更新プログラムのロケールとプールなど) を表示します。インポートされたすべてのデバイス更新ルール (承認待ちのもの、展開 (承認) 済みのもの、取消 (復元) 済みのもの、使用しない (リセットする) と決めたものなど) に関する情報を確認できます。この情報には、Lync Server コントロール パネルまたは Windows PowerShell からアクセスします。

> [!NOTE]
> ルールのインポート、承認、リセット、復元、削除方法の詳細は、「<a href="lync-server-2013-device-update-rules.md">Lync Server 2013 でのデバイス更新ルール</a>」に記載されているトピックを参照してください。


## Lync Server コントロール パネルを使用してデバイス更新ルールを表示するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。Lync Server コントロール パネルを開くために使用できる他の方法の詳細については、「[Lync Server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで \[**クライアント**\] をクリックし、\[**デバイスの更新**\] ナビゲーション ボタンをクリックします。インポートされたルールが \[**デバイスの更新**\] ページに表示されます。

## Windows PowerShell コマンドレットを使用してデバイス更新ルールを表示する

すべてのデバイス更新ルールに関する詳細情報は、Windows PowerShell または **Get-CsDeviceUpdateRule** コマンドレットを使用して表示することもできます。このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモート セッションから実行できます。

> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell」 (<a href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</a>) を参照してください。


## すべてのデバイス更新ルールを表示するには

  - 次のコマンドは、組織で使用するために構成されたすべてのデバイス更新ルールに関する情報を返します。
    
        Get-CsDeviceUpdateRule
    
    コマンドは、デバイス更新ルールごとに次のような情報を返します。
    
        Identity        : Service:WebServer:pool0.vdomain.com/2de8cbf6-9441-4f61-b755-1e4bef1effde
        Id              : 2de8cbf6-9441-4f61-b755-1e4bef1effde
        DeviceType      : UCPhone
        Brand           : Microsoft
        Model           : CPE
        Revision        : A
        Locale          : ENU
        UpdateType      : CPE
        ApprovedVersion :
        RestoreVersion  :
        PendingVersion  : 4.0.7577.4066

## 特定の Web サーバー上のデバイス更新ルールをすべて表示するには

  - 特定のコンピューター上のデバイス更新ルールを表示するには、Filter パラメーターの後にサーバーの ID とワイルドカード文字 (\*) を指定します。たとえば、次のようになります。
    
        Get-CsDeviceUpdateRule -Filter "service:WebServer:atl-cs-001.litwareinc.com*"

詳細については、[Get-CsDeviceUpdateRule](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsDeviceUpdateRule) コマンドレットに関するヘルプ トピックを参照してください。

