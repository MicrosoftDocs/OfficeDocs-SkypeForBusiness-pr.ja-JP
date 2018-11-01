---
title: 'Lync Server 2013: Active Directory ドメイン サービスのサポート'
TOCTitle: Active Directory ドメイン サービスのサポート
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48273265
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 での Active Directory ドメイン サービスのサポート

 

_**トピックの最終更新日:** 2016-12-08_

Lync Server 2013 は、 中央管理ストアを使用して、サーバーとサービスの構成データを格納するので、かつてのように、この情報を得るために Active Directory ドメイン サービス を使用することはありません。 Lync Server 2013 が、AD DS に格納しているのは次の情報です。

  - **スキーマ拡張**
    
      - ユーザー オブジェクトの拡張
    
      - Lync Server 2010 および Office Communications Server 2007 R2 クラスの拡張 (以前サポートされていたバージョンとの下位互換性を保つため)

  - **データ** ( Lync Server 2013 の拡張スキーマおよび既存のクラスに格納)
    
      - ユーザーの SIP URI と他のユーザー設定
    
      - アプリケーションの連絡先オブジェクト ( 応答グループ アプリケーションや 会議アテンダント アプリケーションなど)
    
      - 下位互換性について公開されたデータ
    
      - 中央管理ストアのサービス コントロール ポイント (SCP)
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

ここでは、Lync Server 2013 に対する AD DS のサポート要件について説明します。サポートされているトポロジの詳細については、「サポート」のドキュメントの「[Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。

## サポートされるドメイン コントローラー オペレーティング システム

Lync Server 2013 は、次のオペレーティング システムを実行するドメイン コントローラーをサポートします。

  - Windows Server 2012 R2 オペレーティング システム

  - Windows Server 2012 オペレーティング システム

  - Windows Server 2008 R2 オペレーティング システム

  - Windows Server 2008 オペレーティング システム

  - Windows Server 2008 Enterprise 32 ビット版

  - Windows Server 2003 R2 オペレーティング システムの 32 ビット版または 64 ビット版

  - Windows Server 2003 オペレーティング システムの 32 ビット版または 64 ビット版

## フォレストおよびドメインの機能レベル

Lync Server 2013 を展開するすべてのドメインは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメインの機能レベルに引き上げる必要があります。

Lync Server 2013 を展開するすべてのフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のフォレストの機能レベルに引き上げる必要があります。

## 読み取り専用ドメイン コントローラーのサポート

Lync Server 2013 は、書き込み可能なドメイン コントローラーを使用できる限り、読み取り専用ドメイン コントローラーまたは読み取り専用グローバル カタログ サーバーが含まれる、 Active Directory ドメイン サービス の展開をサポートします。

## ドメイン名

Lync Server は、単一ラベルのドメインをサポートしません。たとえば、ルート ドメイン名が **contoso.local** であるフォレストはサポートされますが、**local** という名前のルート ドメインはサポートされません。詳細については、Microsoft サポート技術情報の記事 300684「単一ラベル DNS 名を使用して Active Directory のドメインを構成する」( <http://go.microsoft.com/fwlink/?linkid=143752>) を参照してください。

> [!NOTE]
> Lync Server では、ドメインの名前変更はサポートしていません。 Lync Server が展開されるドメインの名前を変更する必要がある場合は、最初に Lync Server をアンインストールし、ドメインの名前を変更してから、 Lync Server を再インストールする必要があります。


## ロックダウンされた AD DS 環境

AD DS 環境がロックダウンされると、多くの場合、ユーザー オブジェクトとコンピューター オブジェクトは特定の組織単位 (OU) に置かれ、アクセス許可の継承が無効になります。これで管理業務の安全な委任が促進され、グループ ポリシー オブジェクト (GPO) を使用してセキュリティ ポリシーを執行できるようになります。Lync Server 2013 は、ロックダウンされた Active Directory 環境に展開することができます。ロックダウンされた環境で Lync Server を展開するために必要な機能の詳細については、「展開」のドキュメントの「[Lync Server 2013 でのロックダウンされた Active Directory ドメイン サービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

