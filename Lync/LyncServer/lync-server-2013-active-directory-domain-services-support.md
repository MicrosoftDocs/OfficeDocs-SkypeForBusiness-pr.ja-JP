---
title: 'Lync Server 2013: Active Directory ドメインサービスのサポート'
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
ms.openlocfilehash: 7aada74d1cc96d0dfd7396231ccd96e6ed0d13a6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008559"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-support-in-lync-server-2013"></a>Lync Server 2013 での Active Directory ドメインサービスのサポート

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-11-07_

Lync Server 2013 は、中央管理ストアを使用して、この情報の Active Directory ドメインサービスに依存するのではなく、サーバーとサービスの構成データを格納します。 Lync Server 2013 では、引き続き AD DS に次のものが格納されます。

  - **スキーマ拡張**
    
      - ユーザー オブジェクトの拡張
    
      - 以前サポートされていたバージョンとの下位互換性を維持するための Lync Server 2010 および Office Communications Server 2007 R2 クラスの拡張機能

  - **データ**(Lync Server 2013 の拡張スキーマおよび既存のクラスに格納されている)
    
      - ユーザーの SIP URI と他のユーザー設定
    
      - アプリケーションの連絡先オブジェクト (たとえば、応答グループアプリケーションや会議アテンダントアプリケーション)
    
      - 下位互換性について公開されたデータ
    
      - 中央管理ストアのサービスコントロールポイント (SCP)
    
      - Kerberos 認証のアカウント (オプションのコンピューター オブジェクト)

このセクションでは、Lync Server 2013 の AD DS のサポート要件について説明します。 トポロジのサポートの詳細については、「サポート」のドキュメントの「 [Lync Server 2013 でサポートされている Active Directory トポロジ](lync-server-2013-supported-active-directory-topologies.md)」を参照してください。

<div>

## <a name="supported-domain-controller-operating-systems"></a>サポートされるドメイン コントローラー オペレーティング システム

Lync Server 2013 は、次のオペレーティングシステムを実行しているドメインコントローラーをサポートします。

  - Windows Server 2012 R2 オペレーティングシステム

  - Windows Server 2012 オペレーティングシステム

  - Windows Server 2008 R2 オペレーティング システム

  - Windows Server 2008 オペレーティング システム

  - Windows Server 2008 Enterprise 32-Bit

  - Windows Server 2003 R2 オペレーティング システムの 32 ビット版または 64 ビット版

  - Windows Server 2003 オペレーティングシステムの32ビット版または64ビット版

</div>

<div>

## <a name="forest-and-domain-functional-level"></a>フォレストおよびドメインの機能レベル

Lync Server 2013 を展開するすべてのドメインを、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のドメイン機能レベルに展開する必要があります。

Lync Server 2013 を展開するすべてのフォレストは、Windows Server 2012 R2、Windows Server 2012、Windows Server 2008 R2、Windows Server 2008、または少なくとも Windows Server 2003 のフォレスト機能レベルに上げられる必要があります。

</div>

<div>

## <a name="support-for-read-only-domain-controllers"></a>読み取り専用ドメイン コントローラーのサポート

Lync Server 2013 は、書き込み可能なドメインコントローラーがある限り、読み取り専用ドメインコントローラーまたは読み取り専用グローバルカタログサーバーが含まれる Active Directory ドメインサービスの展開をサポートします。

</div>

<div>

## <a name="domain-names"></a>ドメイン名

Lync Server は、単一ラベルのドメインをサポートしていません。 たとえば、ルート ドメイン名が **contoso.local** であるフォレストはサポートされますが、**local** という名前のルート ドメインはサポートされません。 詳細については、「Microsoft サポート技術情報の記事300684」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=143752](http://go.microsoft.com/fwlink/p/?linkid=143752)。単一ラベル DNS 名のドメインに対する Windows の構成については、「」を参照してください。

<div>


> [!NOTE]  
> Lync Server は、ドメイン名の変更をサポートしていません。 Lync Server が展開されているドメインの名前を変更する必要がある場合は、まず Lync Server をアンインストールしてから、ドメインの名前を変更してから Lync Server を再インストールする必要があります。



</div>

</div>

<div>

## <a name="locked-down-adds-environments"></a>ロックダウンされた AD DS 環境

ロックダウンされた AD DS 環境では、アクセス許可の継承が無効になっている特定の組織単位 (Ou) にユーザーとコンピューターのオブジェクトが配置されることが多く、グループポリシーオブジェクト (Gpo) を使用して実行できるようにすることができます。セキュリティポリシー。 Lync Server 2013 は、ロックダウンされた Active Directory 環境に展開できます。 ロックダウンされた環境で Lync Server を展開するために必要な事項の詳細については、「展開」のドキュメントの「 [Lync server 2013 でのロックダウンされた Active Directory ドメインサービスの準備](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

