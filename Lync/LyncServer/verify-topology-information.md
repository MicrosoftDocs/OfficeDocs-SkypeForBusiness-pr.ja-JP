---
title: トポロジ情報の確認
TOCTitle: トポロジ情報の確認
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48273210
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# トポロジ情報の確認

 

_**トピックの最終更新日:** 2012-09-26_

マージが正常に完了したことを確認する最初のステップは、 Lync Server 2013 でマージした Office Communications Server 2007 R2 トポロジ情報を表示することです。トポロジ ビルダーでは、マージした各 Office Communications Server 2007 R2 プールおよびサーバーの完全修飾ドメイン名 (FQDN) が \[**BackCompatSite**\] ノードに表示されます。

## トポロジ ビルダーで BackCompatSite を表示するには

1.  Office Communications Server 2007 R2 環境で、 Office Communications Server 2007 R2 管理ツールを開き、従来のプールとサーバーの FQDN をすべてメモします。

2.  Lync Server 2013 環境で、トポロジ ビルダーを開き、\[**BackCompatSite**\] ノードを展開します。

3.  マージするプールおよびサーバーの FQDN がすべて表示されていることを確認します。
    
    > [!NOTE]
    > フロントエンド サーバーまたは Standard Edition サーバーに併置されたサーバーの役割に関しては、[<strong>BackCompatSite</strong>] に情報は表示されません。 Office Communications Server 2007 R2 と Lync Server 2013 の相互運用に必要なサーバーの役割だけが表示されます。


![トポロジ ビルダー、\[BackCompatSite\] ダイアログ ボックス](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "トポロジ ビルダー、[BackCompatSite] ダイアログ ボックス")

Lync Server 2013 コントロール パネルを使用して、マージ済みトポロジを表示することもできます。 Lync Server 2013 コントロール パネルで、マージ済みトポロジの各サーバーの FQDN、プールの FQDN、およびサイト名を表示できます。マージされたサーバーの \[**サイト**\] 列には、\[**BackCompatSite**\] という名前が表示されます。

## マージされたトポロジを Lync Server 2013 コントロール パネル で表示するには

1.  Lync Server 2013 コントロール パネルを開きます。

2.  \[**トポロジ**\] をクリックします。

3.  \[**状態**\] タブで、\[**サイト**\] 列の \[**BackCompatSite**\] を見つけて、マージしたサーバーおよびプールが表示されていることを確認します。

![マージ後のトポロジが表示されている Lync Server コントロール パネル](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "マージ後のトポロジが表示されている Lync Server コントロール パネル")

マージされたプールの詳細を表示するには、 **Get-CsPool** コマンドレットを使用します。トポロジ ビルダーおよび Lync Server 2013 コントロール パネルで参照できる情報に加えて、このコマンドレットを使用すると Lync Server 2013 プールで実行されているサービスが表示されます。

> [!NOTE]
> トポロジ ビルダーでマージ ウィザードの実行後にトポロジを公開すると、会議ディレクトリが Lync Server 2013 にマージされます。会議ディレクトリを検証するには、 <strong>Get-CsConferenceDirectory</strong> コマンドレットを実行します。


## マージされたプールのサービスを表示するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    次に例を示します。
    
        Get-CsPool -Identity pool02.contoso.net

## マージされた会議ディレクトリを検証するには

1.  Lync Server 2013 管理シェルを開きます。

2.  コマンドラインで、次のように入力します。
    
        Get-CsConferenceDirectory

3.  マージするプールまたはサーバーの会議ディレクトリが Lync Server 2013 にすべてあることを確認します。

