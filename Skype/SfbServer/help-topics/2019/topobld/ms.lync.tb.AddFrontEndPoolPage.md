---
title: フロントエンド プールの FQDN を追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: 作成するフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。フロント エンド プールを含むトポロジを公開した後でプールの FQDN を変更することはできません。プールの名前変更が必要になった場合は、そのプールを削除してから、新しい FQDN で新しいプールを追加する必要があります。
ms.openlocfilehash: 7b0b14ab9b8cb450a80872cedf61e6f24da91dc2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811657"
---
# <a name="add-front-end-pool-fqdn"></a>フロント エンド プールの FQDN の追加
 
作成するフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。フロント エンド プールを含むトポロジを公開した後でプールの FQDN を変更することはできません。プールの名前変更が必要になった場合は、そのプールを削除してから、新しい FQDN で新しいプールを追加する必要があります。
  
> [!TIP]
> 将来的にフロント エンド プールを実装する予定の場合は、**[複数コンピューターのプール]** を選択してください。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューターのプールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーを再度実行して新しいプール メンバーを定義し、新しいトポロジを公開し、Skype for Business Server 展開ウィザードを使用して新しいフロントエンド プール メンバーを設定する必要があります。 また、プールの該当するロード バランサー (ドメイン ネーム システム (DNS) 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。 多くの場合は、両方の負荷分散システムが用意されています。 両方に新しいメンバー サーバーを追加していることを確認してください。 
  

