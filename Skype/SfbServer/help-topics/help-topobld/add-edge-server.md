---
title: エッジ サーバーを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9bd9c2b2-8329-4b31-a937-e462f5cc7293
description: トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジ サーバーまたはエッジ サーバー プールを含むトポロジを発行し、Skype for Business Server をインストールする前に、外部ユーザー アクセスを展開するためのすべての前提条件を完了している必要があります。 これらの前提条件の詳細については、「展開」のドキュメントの「Preparing for Installation of Servers in the Perimeter Network」を参照してください。
ms.openlocfilehash: 49e4a8a9dd6bd9fcd09332f062cb7646c47dac03
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114263"
---
# <a name="add-edge-server"></a>エッジ サーバーの追加

トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジ サーバーまたはエッジ サーバー プールを含むトポロジを発行し、Skype for Business Server をインストールする前に、外部ユーザー アクセスを展開するためのすべての前提条件を完了している必要があります。 これらの前提条件の詳細については、「展開」のドキュメントの「[Preparing for Installation of Servers in the Perimeter Network](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network)」を参照してください。

> [!IMPORTANT]
> 指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。エッジ サーバーまたはエッジ サーバー プールとして展開するドメインに参加していないコンピューターの名前に、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。

> [!TIP]
> 今後、エッジ サーバー プールを実装するように予定している場合は、[**複数コンピューターのプール**] を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューターのプールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーで新しいプール メンバーを定義し、新しいトポロジを発行し、Skype for Business Server 展開ウィザードを使用して新しいエッジ サーバー プール メンバーをセットアップする必要があります。 また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。 1 つのいエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。 適切なロード バランサーに新しいメンバー サーバーを必ず追加してください。

初期トポロジの展開時や初期トポロジの展開後に、外部ユーザー アクセスのサポートを追加できます。 既存のトポロジへのエッジ サーバーまたはエッジ サーバー プールの追加の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology)」を参照してください。