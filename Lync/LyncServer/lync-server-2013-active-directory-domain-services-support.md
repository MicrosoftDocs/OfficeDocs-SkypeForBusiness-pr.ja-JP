---
title: 'Lync Server 2013: Active Directory ドメイン サービスのサポート'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services support
ms:assetid: aeb62d5e-e424-473a-b795-9452150c98dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412831(v=OCS.15)
ms:contentKeyID: 48185136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32e1bce2546512900efb0b5ecd1256a97adde41e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737017"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 での Active Directory ドメイン サービスのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-11-07_

Lync Server 2013 は、この情報について Active Directory ドメインサービスに依存するのではなく、サーバーとサービスの構成データを保存するために、中央管理ストアを使用しています。 Lync Server 2013 では、引き続き次の内容が AD DS に保存されています。

  - **スキーマ拡張**
    
      - ユーザー オブジェクトの拡張
    
      - 以前サポートされているバージョンとの下位互換性を維持するための、Lync Server 2010 および Office Communications Server 2007 R2 クラス用の拡張機能

  - **データ**(Lync Server 2013 拡張スキーマと既存のクラスに保存されている)
    
      - ユーザーの SIP URI と他のユーザー設定
    
      - アプリケーションの連絡先オブジェクト (たとえば、応答グループのアプリケーション、会議アテンダントアプリケーションなど)
    
      - 下位互換性のために公開されたデータ
    
      - 中央管理ストアのサービス制御ポイント (SCP)
    
      - Kerberos 認証アカウント (オプションのコンピューターオブジェクト)

このセクションでは、Lync Server 2013 の AD DS のサポート要件について説明します。 トポロジのサポートの詳細については、サポートドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。

<div>

## <a name="supported-domain-controller-operating-systems"></a>サポートされているドメインコントローラーオペレーティングシステム

Lync Server 2013 は、次のオペレーティングシステムを実行しているドメインコントローラーをサポートしています。

  - Windows Server 2012 R2 オペレーティングシステム

  - Windows Server 2012 オペレーティングシステム

  - Windows Server 2008 R2 オペレーティング システム

  - Windows Server 2008 オペレーティング システム

  - Windows Server 2008 Enterprise 32 ビット

  - Windows Server 2003 R2 オペレーティングシステムの32ビットまたは64ビットバージョン

  - Windows Server 2003 オペレーティングシステムの32ビットまたは64ビットバージョン

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>フォレストとドメインの機能レベル

Lync Server 2013 を展開するすべてのドメインを、windows server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または Windows Server 2003 以上のドメインの機能レベルに展開する必要があります。

Lync Server 2013 を展開するすべてのフォレストは、Windows Server 2012 R2、windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または Windows Server 2003 以上のフォレストの機能レベルに上げる必要があります。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>読み取り専用ドメインコントローラーのサポート

Lync Server 2013 は、書き込み可能なドメインコントローラーが利用可能であれば、読み取り専用のドメインコントローラーまたは読み取り専用のグローバルカタログサーバーを含む Active Directory ドメインサービスの展開をサポートしています。

</div>

<div>

## <a name="domain-names"></a>ドメイン名

Lync Server では、単一ラベルのドメインはサポートされていません。 たとえば、 **local**という名前のルートドメインを持つフォレストはサポートされていますが、 **local**という名前のルートドメインはサポートされていません。 詳細については、「Microsoft サポート技術情報の記事300684」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。 "単一ラベルの DNS 名でドメイン用に Windows を構成する" について説明します。

<div>


> [!NOTE]  
> Lync Server では、ドメイン名の変更はサポートされていません。 Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから、Lync Server を再インストールする必要があります。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>ロックダウンされた AD DS 環境

ロックダウンされた AD DS 環境では、管理者の委任を保護し、グループポリシーオブジェクト (Gpo) の使用を有効にするために、ユーザーとコンピューターオブジェクトが特定の組織単位 (Ou) に配置されることがよくあります。セキュリティポリシー。 Lync Server 2013 は、ロックダウンされた Active Directory 環境に展開できます。 ロックダウン環境での Lync Server の展開に必要なものについて詳しくは、「展開ドキュメントの[Lync server 2013 でロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」をご覧ください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

