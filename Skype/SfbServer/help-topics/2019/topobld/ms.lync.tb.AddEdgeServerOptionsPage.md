---
title: エッジ サーバーのオプションを追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerOptionsPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 2405f227-4297-40d0-a117-55427a9e4052
ROBOTS: NOINDEX, NOFOLLOW
description: エッジ プールで有効にする各機能を選択します。 既定では、エッジ プールは、仮想プライベート ネットワーク (VPN) を使用してファイアウォールの外部からサインインする組織内のリモート ユーザーをサポートします。 以下のエッジ プール機能オプションも使用できます。
ms.openlocfilehash: 9ac07d7a15e138c3fe817aab6754ca098f8ff774
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60834485"
---
# <a name="add-edge-server-options"></a>エッジ サーバー オプションの追加

エッジ プールで有効にする各機能を選択します。 既定では、エッジ プールは、仮想プライベート ネットワーク (VPN) を使用してファイアウォールの外部からサインインする組織内のリモート ユーザーをサポートします。 以下のエッジ プール機能オプションも使用できます。

- アクセス エッジ サービス、Web 会議エッジ サービス、音声ビデオ エッジ サービスなど、すべてのエッジ サービスに 1 つの完全修飾ドメイン名 (FQDN) と IP アドレスを使用する。1 つの FQDN と IP アドレスを使用するオプションを選択しない場合、展開プロセスの一貫として、これらの 3 つの各エッジ サービスに個別の FQDN と IP アドレスを指定する必要があります。エッジ サービスの詳細については、「計画」のドキュメントの「[Components Required for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-components-required-for-external-user-access)」を参照してください。

    > [!NOTE]
    > このオプションを選択する場合、各エッジ サービスに異なるポート番号を指定する必要があります (推奨される既定のポート設定:アクセス エッジ サービスに 444、Web 会議エッジ サービスに 8057、音声ビデオ エッジ サービスに 443)。このオプションを選択すると、潜在的な接続の問題を防ぐとともに、3 つのすべてのサービスに 1 つの FQDN を入力できるため、構成を簡素化することができます。

- フェデレーションのサポート。内部ユーザーと組織外部の信頼されるドメインのユーザー (サポートされるパブリック インスタント メッセージング (IM) プロバイダーのユーザーなど) との間の通信をサポートする必要がある場合は、このオプションを選択します。このオプションを選択する場合、サポートする必要がある特定のフェデレーション ドメインとパブリック IM 接続サービス プロバイダーのサポートを構成する必要があります。フェデレーションおよびその他の種類の外部ユーザー アクセスのサポートの構成の詳細については、「エッジ サーバーの展開」のドキュメントの「[Configuring Support for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-support-for-external-user-access)」を参照してください。

    > [!NOTE]
    > 組織内の 1 つのフロントエンド プールまたは Standard エッジ サーバーのみ、フェデレーション用に外部に公開できます。パブリック IM ユーザーを含め、フェデレーション ユーザーによるすべてのアクセスが同じエッジ プールまたは単一エッジサーバーを通過します。たとえば、ニューヨークとロンドンにそれぞれ展開されているエッジ プールまたは単一エッジ サーバーが展開に含まれている場合、ニューヨークのエッジ プールまたは単一エッジ サーバーでフェデレーション サポートを有効にすると、フェデレーション ユーザーの信号トラフィックはニューヨークのエッジ プールまたは単一エッジ サーバーを通過します。これは、ロンドンのユーザーとの通信の場合でも同じです。ただし、ロンドンの内部ユーザーがロンドンのフェデレーション ユーザーを呼び出す場合は、音声ビデオ トラフィックにロンドンのプールまたはエッジ サーバーを使用します。

- XMPP フェデレーションを有効にします。内部ユーザーと信頼された XMPP パートナーとの間の通信をサポートする場合は、このオプションを選択します。

最初のトポロジの展開時やその後に、外部ユーザー アクセスのサポートを追加できます。既存のトポロジにエッジ サーバーを追加する方法の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)」を参照してください。