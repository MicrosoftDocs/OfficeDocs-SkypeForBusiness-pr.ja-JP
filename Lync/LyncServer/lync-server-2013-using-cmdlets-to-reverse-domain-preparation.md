---
title: 'Lync Server 2013: コマンドレットの使用によるドメインの準備の無効化'
TOCTitle: コマンドレットの使用によるドメインの準備の無効化
ms:assetid: 014dba5d-fcb3-44c9-9d63-ae0755276dac
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398071(v=OCS.15)
ms:contentKeyID: 48271062
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化

 

_**トピックの最終更新日:** 2012-10-29_

**Disable-CsAdDomain** コマンドレットを使用して、ドメインの準備ステップを元に戻します。

## コマンドレットを使用してドメインの準備を元に戻すには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

3.  次のコマンドレットを実行します。
    
        Disable-CsAdDomain [-Domain <Fqdn>] [-DomainController <Fqdn>] [-Force <SwitchParameter>] 
        [-GlobalCatalog <Fqdn>] [-GlobalSettingsDomainController <Fqdn>] 
    
    次に例を示します。
    
        Disable-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.net -Force
    
    Force パラメーターが指定された場合は、ドメイン内の フロント エンド サーバーまたは 音声ビデオ会議サーバー が 1 つ以上アクティブになっていても、ドメインの準備はロールバックされます。Force パラメーターが指定されなかった場合は、ドメイン内の フロント エンド サーバーまたは 音声ビデオ会議サーバーのいずれかがアクティブになると、ドメインの準備のロールバックが終了します。
    
    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する Active Directory フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、AD DS の任意のドメイン コントローラーを参照します。


## 関連項目

#### タスク

[Lync Server 2013 のドメイン準備手続き](lync-server-2013-running-domain-preparation.md)  

#### その他のリソース

[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

