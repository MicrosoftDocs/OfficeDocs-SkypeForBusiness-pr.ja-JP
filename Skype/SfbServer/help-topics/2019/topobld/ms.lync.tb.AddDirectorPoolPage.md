---
title: ディレクター プールを追加する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクター プールの FQDN を定義するには、負荷分散されたプール内の 2 つ以上のディレクターで構成される複数コンピューター プールまたは単一コンピューター プールを選択します。 また、ディレクター プールまたは単一ディレクターの FQDN への接続に使用する完全修飾ドメイン名 (FQDN) も入力する必要があります。 ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。
ms.openlocfilehash: 99b0aa59e6db5c35a892ac3df19abb38831a11c0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49807757"
---
# <a name="add-director-pool"></a>ディレクター プールの追加
 
**ディレクター プールの FQDN を定義する** には、負荷分散されたプール内の 2 つ以上のディレクターで構成される **複数コンピューター プール** または **単一コンピューター プール** を選択します。 また、ディレクター プールまたは単一ディレクターの FQDN への接続に使用する完全修飾ドメイン名 (FQDN) も入力する必要があります。 ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。
  
> [!TIP]
> 今後、ディレクター プールを実装することを予定している場合は、[**複数のコンピューター プール**] を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーを再度実行して新しいプール メンバーを定義し、新しいトポロジを公開し、Skype for Business Server 展開ウィザードを使用して新しいディレクター プール メンバーをセットアップする必要があります。 また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。 多くの場合、両方の負荷分散システムを使用します。 両方に新しいメンバー サーバーを追加していることを確認してください。 
  

