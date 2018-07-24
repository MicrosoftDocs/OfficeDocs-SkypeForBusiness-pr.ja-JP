---
title: フロント エンド プールの FQDN を追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: 作成しているフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。 フロント エンド プールを含むトポロジを公開した後は、プールの FQDN を変更できません。 プールの名前を変更する場合は、プールを削除し、新しい FQDN を持つ新しいプールを追加します。
ms.openlocfilehash: 739a794b1b3fd8e88ae074b5c03f4c0e51fb844f
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981298"
---
# <a name="add-front-end-pool-fqdn"></a>フロント エンド プールの FQDN を追加します。
 
作成しているフロント エンド プールの完全修飾ドメイン名 (FQDN) を指定します。 フロント エンド プールを含むトポロジを公開した後は、プールの FQDN を変更できません。 プールの名前を変更する場合は、プールを削除し、新しい FQDN を持つ新しいプールを追加します。
  
> [!TIP]
> フロント エンド プールを将来的に実装する場合は、**複数コンピューターのプール**を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 プールに後でより多くのコンピューターを追加する準備ができたら、新しいプールのメンバーを定義、ビジネス サーバーの展開ウィザードは、Skype を使用して新しいフロント エンド プール メンバーを設定して、新しいトポロジを公開するもう一度トポロジ ビルダーを実行してください。 プール、ドメイン ネーム システム (DNS) 負荷分散またはハードウェア ロード バランサーの適切な負荷分散装置に新しいプールのメンバーを追加することもあります。 多くの場合に、両方の負荷分散のシステムで必要があります。 両方に新しいメンバー サーバーを追加していることを確認します。 
  

