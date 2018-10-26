---
title: Exchange ユニファイド メッセージングの連絡先オブジェクトの移動
TOCTitle: Exchange ユニファイド メッセージングの連絡先オブジェクトの移動
ms:assetid: 35c7e987-41b5-4798-b617-3303f20e52e3
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ688022(v=OCS.15)
ms:contentKeyID: 49886915
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exchange ユニファイド メッセージングの連絡先オブジェクトの移動

 

_**トピックの最終更新日:** 2012-10-19_

自動応答 (AA) およびサブスクライバー アクセス (SA) の連絡先オブジェクトを新しい Lync Server 2013 の展開に移行するには、最初に、 **Get-CsExUmContact** および **Move-CsExUmContact** コマンドレットを使用して、従来の Office Communications Server 2007 R2 の展開から新しい Lync Server 2013 の展開にオブジェクトを移動する必要があります。その後、Exchange Server において、 **ExchUCUtil**Windows PowerShell スクリプトを実行して、新しく展開された Lync プールで以下を行います。

  - ユニファイド メッセージング IP ゲートウェイに追加します。

  - ユニファイド メッセージング ハント グループに追加します。

> [!NOTE]
> <strong>Get-CsExUmContact</strong> および <strong>Move-CsExUmContact</strong> コマンドレットを使用するには、RTCUniversalUserAdmins グループのメンバーであり、連絡先オブジェクトを格納する組織単位 (OU) に対する OU アクセス許可を持っている必要があります。OU アクセス許可は <strong>Grant-OUPermission</strong> コマンドレットを使用して付与できます。


## Lync Server 管理シェルを使用して連絡先オブジェクトを移動するには

1.  Lync Server 管理シェルを開きます。

2.  Exchange UM で登録された各プールについて (pool1.contoso.net は Office Communications Server 2007 R2 の展開のプール、pool2.contoso.net は Lync Server 2013 の展開のプール) について、コマンド ラインで次のように入力します。
    
        Get-CsExUmContact -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsExUmContact -Target pool02.contoso.net
    
    連絡先オブジェクトが移動されたことを確認するには、 **Get-CsExumContact** コマンドレットを実行し、 **RegistrarPool** が新しいプールを参照していることを確認します。

## Windows PowerShell の ExchUCUtil スクリプトを実行するには

1.  Exchange 組織管理者特権のあるユーザーとして Exchange UM Server にログオンします。

2.  Windows PowerShell の ExchUCUtil スクリプトがある場所に移動します。
    
    Exchange 2007 では、ExchUCUtil.ps1 が **%Program Files%\\Microsoft\\Exchange Server\\Scripts\\ExchUCUtil.ps1** にあります。
    
    Exchange 2010 では、ExchUCUtil.ps1 が **%Program Files%\\Microsoft\\Exchange Server\\V14\\Scripts\\ExchUCUtil.ps1** にあります。

3.  Exchange が単一のフォレストに展開されている場合は、次のように入力します。
    
        exchucutil.ps1
    
    Exchange を複数のフォレストに展開する場合は、次のように入力します。
    
        exchucutil.ps1 -Forest:" <forest FQDN>"
    
    *フォレスト FQDN* には、Lync Server 2013 を展開するフォレストを指定します。
    

    > [!IMPORTANT]
    > exchucutil.ps1 を実行した後で、<STRONG>Lync Server フロントエンド</STRONG> サービス (rtcsrv.exe) を再起動してください。再起動しないと、Lync Server 2013 でトポロジのユニファイド メッセージングが検出されません。


