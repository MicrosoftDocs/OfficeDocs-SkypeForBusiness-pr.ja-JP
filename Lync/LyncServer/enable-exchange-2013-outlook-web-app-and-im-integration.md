---
title: Exchange 2013 Outlook Web App および IM 統合の有効化
TOCTitle: Exchange 2013 Outlook Web App および IM 統合の有効化
ms:assetid: 44d08cf0-b17d-46e1-a4f0-fcc2fe96a958
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/JJ204857(v=OCS.15)
ms:contentKeyID: 48271933
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Exchange 2013 Outlook Web App および IM 統合の有効化

 

_**トピックの最終更新日:** 2012-10-19_

Lync Server 2013 で Exchange 2013 の Outlook Web Access (OWA) およびインスタント メッセージング (IM) 統合を有効にするには、Exchange 2013 クライアント アクセス サーバー (CAS) のサーバーを、信頼済みアプリケーション サーバーとして Lync Server 2013 トポロジに追加する必要があります。

## 信頼済みアプリケーション プールを作成するには

1.  Lync Server 2013 管理シェルを開始します。

2.  次のコマンドレットを実行します。
    
        Get-CsSite
    
    これで、プールを作成する siteName に対応する siteID が取得されます。詳細については、Lync Server 2013 管理シェルのドキュメントの「[Get-CsSite](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsSite)」を参照してください。

3.  次のコマンドレットを実行します。
    
        New-CsTrustedApplicationPool -Identity <E14 CAS FQDN> -ThrottleAsServer $true -TreatAsAuthenticated $true -ComputerFQDN <E14 CAS FQDN> -Site <Site> -Registrar <Pool FQDN in the site> -RequiresReplication $false
    
    詳細については、Lync Server 2013 管理シェルのドキュメントの「[New-CsTrustedApplicationPool](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplicationPool)」を参照してください。
    
    Exchange Server の FQDN を Exchange OWA 証明書のサブジェクト名 (SN) またはサブジェクトの別名 (SAN) として構成する必要があります。
    
    Exchange OWA で、プールの FQDN も信頼されていることを確認します。
    

    > [!IMPORTANT]
    > CAS サーバーが、Exchange 2013 ユニファイド メッセージング (UM) を実行しているのと同じサーバー上に併置されていない場合には、この手順の残りの作業は省略し、この後の「Exchange 2013 CAS サーバー向けの信頼済みアプリケーションの作成」の手順を実行します。CAS サーバーが、Exchange 2013 ユニファイド メッセージング (UM) を実行しているのと同じサーバー上に併置されている場合には、この手順の残りの作業を実行し、この後の「Exchange 2013 CAS サーバー向けの信頼済みアプリケーションの作成」の手順は省略します。



4.  **Enable-CsTopology** を実行します。

5.  トポロジ ビルダーを開き、既存のトポロジをダウンロードします。

6.  左側のウィンドウで、\[**信頼済みアプリケーション サーバー**\] が表示されるまでツリーを展開します。

7.  \[**信頼されたアプリケーション サーバー**\] ノードを展開します。

8.  Exchange 2013 CAS サーバーが信頼済みアプリケーション サーバーとして表示されます。

## Exchange 2013 CAS サーバーに対して信頼済みアプリケーションを作成するには

1.  Lync Server 2013 管理シェルを開始します。

2.  CAS サーバーが、Exchange 2013 ユニファイド メッセージング (UM) を実行しているのと同じサーバー上に併置されていない場合には、次のコマンドレットを実行します。
    
        New-CsTrustedApplication -ApplicationId <AppID String> -TrustedApplicationPoolFqdn <E14 CAS FQDN> -Port <available port number>
    
    詳細については、Lync Server 2013 管理シェルのドキュメントのトピック「[New-CsTrustedApplication](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrustedApplication)」を参照してください。

3.  **Enable-CsTopology** を実行します。

4.  トポロジ ビルダーの左側のウィンドウで、\[**信頼済みアプリケーション サーバー**\] が表示されるまでツリーを展開します。

5.  \[**信頼されたアプリケーション サーバー**\] ノードを展開します。

6.  Exchange 2013 CAS サーバーが信頼済みアプリケーション サーバーとして表示されます。

