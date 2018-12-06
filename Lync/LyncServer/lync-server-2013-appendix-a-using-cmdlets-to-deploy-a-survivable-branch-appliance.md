---
title: 'Lync Server 2013: 付録 A: コマンドレットを使用した存続可能ブランチ アプライアンスの展開'
TOCTitle: '付録 A: コマンドレットを使用した存続可能ブランチ アプライアンスの展開'
ms:assetid: 796a26cf-7ec9-453b-8757-6153a6dd86c5
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398598(v=OCS.15)
ms:contentKeyID: 48272575
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 付録 A: Lync Server 2013 でのコマンドレットを使用した存続可能ブランチ アプライアンスの展開

 

_**トピックの最終更新日:** 2012-10-07_

このトピックでは、Lync Server 管理シェルを使用して 存続可能ブランチ アプライアンスを展開する方法について説明します。中央サイトでこの手順を実行します。

## 存続可能ブランチ アプライアンスをリモートで展開するには

1.  「[Lync Server 2013 でのトポロジへのブランチ サイトの追加](lync-server-2013-add-branch-sites-to-your-topology.md)」の手順に従って、新しいブランチ サイトを追加します。

2.  ブランチ サイトをドメインに参加させます。

3.  RTCUniversalSBATechnicians グループをローカルの Administrators グループに追加します。

4.  サーバーを再起動し、RTCUniversalSBATechnicians グループのメンバーとしてサーバーにログオンします。

5.  Lync Server 管理シェルで、次のコマンドを入力します。プレースホルダーには、各組織に適した情報を指定します。
    
        Export-CsConfiguration -FileName C:\CSConfig.zip
        Import-CsConfiguration -LocalStore -FileName C:\CSConfig.zip -Verbose
        Enable-CSReplica -Verbose
        Enable-CsComputer -Verbose
        Request-CsCertificate -New -Type default -CA <YourCA> -Verbose
        Set-CsCertificate -Type Default -Thumbprint <YourCertThumbprint>
        Start-cswindowsservice -verbose

