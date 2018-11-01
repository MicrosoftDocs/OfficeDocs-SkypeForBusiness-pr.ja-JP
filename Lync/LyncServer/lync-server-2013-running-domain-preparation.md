---
title: 'Lync Server 2013: ドメイン準備手続き'
TOCTitle: ドメイン準備手続き
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48272902
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 のドメイン準備手続き

 

_**トピックの最終更新日:** 2013-04-16_

セットアップまたは Lync Server 管理シェル コマンドレットを使用すると、ドメインを準備できます。ドメインを準備するコマンドレットは **Enable-CsAdDomain** です。

ドメインの準備は、 Lync Server 2013 用の Active Directory ドメイン サービス を準備する際の最後のステップです。

## セットアップを使ってドメインを準備するには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server 2013 のインストール フォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを起動します。

3.  \[**Active Directory の準備**\] をクリックし、展開状態が判別されるまで待ちます。

4.  \[手順 5: **現在のドメインの準備**\] で、\[**実行**\] をクリックします。

5.  \[**ドメインの準備**\] ページで、\[**次へ**\] をクリックします。

6.  \[**コマンドの実行**\] ページで \[**タスク状態: 完了**\] を見つけて、\[**ログの表示**\] をクリックします。

7.  \[**アクション**\] 列で \[**ドメインの準備**\] を展開します。各タスクの末尾に \[**\<成功\>**\] の実行結果が表示されているかどうかを調べ、ドメインの準備が正常に完了したことを確認します。その後、ログを閉じて \[**完了**\] をクリックします。

8.  Active Directory のレプリケーションが完了するまで待機するか、フォレストのルート ドメイン コントローラーの Active Directory サイトとサービス スナップインに表示されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行します。

## コマンドレットを使用してドメインを準備するには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server コア コンポーネントを次の手順でインストールします。
    
    1.  Lync Server 2013 のインストール フォルダーまたはメディアから、Setup.exe を実行して Lync Server 展開ウィザードを起動します。
    
    2.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、\[**はい**\] をクリックします。
    
    3.  Lync Server 2013 セットアップ ダイアログ ボックスが、 Lync Server ファイルをインストールする場所を求めるメッセージを表示します。既定の場所を選択するか、または好みの場所を \[**参照**\] で選択し、\[**インストール**\] をクリックします。
    
    4.  \[使用許諾契約書\] ページで \[**使用許諾契約書に同意します**\] チェック ボックスをオンにし、\[**OK**\] をクリックします。インストーラーが Lync Server 2013 コア コンポーネントをインストールします。

3.  Lync Server 管理シェルを以下の手順で起動します。\[**スタート**\]、\[**すべてのプログラム**\]、\[**Microsoft Lync Server 2013**\]、\[**Lync Server 管理シェル**\] の順にクリックします。

4.  次のコマンドレットを実行します。
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    次に例を示します。
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Domain パラメーターを指定しない場合、既定値はローカル ドメインになります。

5.  ドメインの準備が成功したことを確認します。次のコマンドレットを実行します。
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    次に例を示します。
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    > [!NOTE]
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。設定をシステム コンテナーに保存する (構成コンテナーにグローバル設定を移行していないアップグレードの展開で一般的) 場合、使用する Active Directory フォレストのルートに 1 つのドメイン コントローラーを定義します。グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。このパラメーターを指定しない場合、コマンドレットでは、設定が構成コンテナーに保存されていると見なして、AD DS の任意のドメイン コントローラーを参照します。
    
    **Domain** パラメーターを指定しない場合、既定値はローカル ドメインになります。
    
    ドメインの準備が成功した場合、このコマンドレットは **LC\_DOMAINSETTINGS\_STATE\_READY** という値を返します。

## 関連項目

#### タスク

[Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  

#### その他のリソース

[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)

