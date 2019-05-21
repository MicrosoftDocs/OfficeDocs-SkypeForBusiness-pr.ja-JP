---
title: フロントエンド プールの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 作成するフロントエンドプールの完全修飾ドメイン名 (FQDN) を指定します。 プールの FQDN は、フロントエンドプールが含まれているトポロジを公開した後に変更することはできません。 プールの名前を変更する必要がある場合は、プールを削除し、新しい FQDN で新しいプールを追加する必要があります。
ms.openlocfilehash: 058e1cc6a1e510ba57bb28a694a9ddc7e9759f90
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275361"
---
# <a name="add-front-end-pool-fqdn"></a>フロントエンド プールの FQDN の追加
 
作成するフロントエンドプールの完全修飾ドメイン名 (FQDN) を指定します。 プールの FQDN は、フロントエンドプールが含まれているトポロジを公開した後に変更することはできません。 プールの名前を変更する必要がある場合は、プールを削除し、新しい FQDN で新しいプールを追加する必要があります。
  
> [!TIP]
> 今後、フロントエンドプールを実装する予定がある場合は、[**複数のコンピュータープール**] を選びます。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジビルダーをもう一度実行して、新しいプールメンバーを定義し、新しいトポロジを公開し、Skype for Business Server Deployment ウィザードを使って新しいフロントエンドプールメンバーを設定する必要があります。 プール、ドメインネームシステム (DNS) 負荷分散、またはハードウェアロードバランサーの適切なロードバランサーに新しいプールメンバーを追加する必要もあります。 多くの場合、両方の負荷分散システムが用意されています。 新しいメンバーサーバーを両方に追加していることを確認してください。 
  

