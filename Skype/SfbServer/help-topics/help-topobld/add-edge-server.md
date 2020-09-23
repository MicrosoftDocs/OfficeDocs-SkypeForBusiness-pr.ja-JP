---
title: エッジ サーバーを追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジサーバーまたはエッジサーバープールを含むトポロジを公開して、Skype for Business Server をインストールする前に、外部ユーザーアクセスを展開するためのすべての前提条件を完了しておく必要があります。 これらの前提条件の詳細については、「展開」のドキュメントの「Preparing for Installation of Servers in the Perimeter Network」を参照してください。
ms.openlocfilehash: 379c181336ecc855feb1344e3328a8ffcd38f447
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216748"
---
# <a name="add-edge-server"></a>エッジ サーバーを追加する

トポロジ設計にエッジ サーバーまたはエッジ サーバー プールを含めるには、エッジ サーバーまたはエッジ サーバー プールを展開するサーバーの完全修飾ドメイン名 (FQDN) を指定する必要があります。 エッジサーバーまたはエッジサーバープールを含むトポロジを公開して、Skype for Business Server をインストールする前に、外部ユーザーアクセスを展開するためのすべての前提条件を完了しておく必要があります。 これらの前提条件の詳細については、「展開」のドキュメントの「[Preparing for Installation of Servers in the Perimeter Network](https://technet.microsoft.com/library/5e6c457a-f964-4ef7-a709-97abda9c673a.aspx)」を参照してください。

> [!IMPORTANT]
> 指定する名前が、サーバーに構成されているコンピューター名と同じである必要があります。既定では、ドメインに参加していないコンピューターのコンピューター名は、FQDN ではなく短い名前です。トポロジ ビルダーでは、短い名前ではなく FQDN を使用します。エッジ サーバーまたはエッジ サーバー プールとして展開するドメインに参加していないコンピューターの名前に、ドメイン ネーム システム (DNS) サフィックスを構成する必要があります。

> [!TIP]
> 今後、エッジ サーバー プールを実装するように予定している場合は、[**複数コンピューターのプール**] を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューターのプールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、もう一度トポロジビルダーを使用して、新しいプールメンバーを定義し、新しいトポロジを公開して、Skype for Business Server の展開ウィザードを使用して新しいエッジサーバープールメンバーを設定する必要があります。 また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。 内部エッジ インターフェイスと外部エッジ インターフェイスでは、同じ種類のロード バランシングを使用する必要があります。 1 つのいエッジ インターフェイスで DNS ロード バランシングを使用し、もう 1 つのエッジ インターフェイスでロード バランサー機器を使用することはできません。 適切なロード バランサーに新しいメンバー サーバーを必ず追加してください。

初期トポロジの展開時や初期トポロジの展開後に、外部ユーザー アクセスのサポートを追加できます。 既存のトポロジへのエッジ サーバーまたはエッジ サーバー プールの追加の詳細については、「エッジ サーバーの展開」のドキュメントの「[Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx)」を参照してください。


