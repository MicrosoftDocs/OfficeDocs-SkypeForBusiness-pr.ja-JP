---
title: 'Lync Server 2013: 社内ユニファイド メッセージングのコンポーネントとトポロジ'
TOCTitle: 社内ユニファイド メッセージングのコンポーネントとトポロジ
ms:assetid: 22fc87cf-a7e5-4c8c-bb9b-101e5380cdcf
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg425711(v=OCS.15)
ms:contentKeyID: 48271567
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 の社内ユニファイド メッセージングのコンポーネントとトポロジ

 

_**トピックの最終更新日:** 2012-09-25_

このトピックでは、Lync Server 2013 展開に Exchange ユニファイド メッセージング (UM) 機能を提供するために必要な Microsoft Exchange Server 2013 のコンポーネントについて説明します。また、内部設置型 Exchange UM 統合でサポートされるトポロジについても説明します。

## Exchange Server コンポーネント

「[統合ユニファイド メッセージングと Lync Server 2013 の機能](lync-server-2013-features-of-integrated-unified-messaging.md)」に記載されている Exchange UM の機能とサービスを組織の エンタープライズ VoIP ユーザーに提供するには、ユーザーのメールボックスをホストし、電子メールとボイス メール用の 1 つの保管場所を提供する Microsoft Exchange メールボックス サーバーとクライアント アクセス サーバーを展開する必要があります。Exchange UM は、Exchange メールボックス サーバーとクライアント アクセス サーバー上のサービスとして実行されます。

Microsoft Exchange Server 2007 および Microsoft Exchange Server 2010 の Exchange UM のコンポーネントの詳細については、「展開」のドキュメントの「[内部設置型 Exchange UM を展開して Lync Server 2013 ボイス メールを提供する](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)」を参照してください。

## サポートされるトポロジ

Lync Server 2013 と Exchange ユニファイド メッセージング (UM) は同じフォレストまたは複数のフォレストに展開できます。展開を複数のフォレストにまたがるようにする場合は、Exchange UM フォレストごとに、Exchange の統合ステップを実行する必要があります。さらに、各 Microsoft Exchange フォレストが Lync Server 2013 フォレストを、Lync Server 2013 フォレストが各 Exchange UM フォレストを信頼するように構成する必要があります。このフォレストの信頼構成に加えて、すべてのユーザーの Exchange UM 設定を、Lync Server 2013 フォレスト内のユーザー オブジェクトに対して設定する必要があります。

Lync Server 2013 は、Exchange UM 統合で次のトポロジをサポートします。

  - 単一のフォレスト

  - 単一ドメイン (すなわち、単一ドメインを含む単一フォレスト)。Lync Server 2013、Microsoft Exchange、およびユーザーが、すべて同じドメインに存在します。

  - 複数ドメイン (すなわち、1 つ以上の子ドメインを備えるルート ドメイン)。Lync Server 2013、および Microsoft Exchange サーバーは、ユーザーを作成しているドメインとは異なるドメインに展開され、Exchange UM サーバーは、サポートする Lync Server 2013 プールとは別のドメインに展開できます。

  - 複数のフォレスト (すなわち、リソース フォレスト)。Lync Server 2013 が、単一フォレストに展開され、その後、ユーザーが複数のフォレストに分散されます。ユーザーの Exchange UM 属性を、Lync Server 2013 フォレストにレプリケートする必要があります。
    
    > [!NOTE]
    > Exchange は複数のフォレストに展開できます。各 Exchange 組織が Exchange UM をそのユーザーに提供するか、または Exchange UM を Lync Server 2013 と同じフォレストに展開できます。

