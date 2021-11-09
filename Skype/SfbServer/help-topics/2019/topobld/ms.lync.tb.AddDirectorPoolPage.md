---
title: ディレクター プールを追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
ROBOTS: NOINDEX, NOFOLLOW
description: ディレクター プールの FQDN を定義するには、負荷分散されたプール内の 2 つ以上のディレクターで構成される複数コンピューター プールまたは単一コンピューター プールを選択します。 ディレクター プールまたは単一ディレクターの FQDN への接続に使用する完全修飾ドメイン名 (FQDN) も入力する必要があります。 ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。
ms.openlocfilehash: 70df13a0339c11d47e907ff70be395f613cdb1fe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60839339"
---
# <a name="add-director-pool"></a>ディレクター プールの追加
 
**ディレクター プールの FQDN を定義する** には、負荷分散されたプール内の 2 つ以上のディレクターで構成される **複数コンピューター プール** または **単一コンピューター プール** を選択します。 ディレクター プールまたは単一ディレクターの FQDN への接続に使用する完全修飾ドメイン名 (FQDN) も入力する必要があります。 ディレクター コンピューターのプールの場合、これはロード バランサー機器の仮想 IP アドレスのドメイン ネーム システム (DNS) エントリまたは DNS 負荷分散の DNS エントリです。
  
> [!TIP]
> 今後、ディレクター プールを実装することを予定している場合は、[**複数のコンピューター プール**] を選択します。 プールが負荷分散された 2 つ以上のコンピューターとして定義されている場合でも、単一コンピューター プールを作成して、単一コンピューターにプールの FQDN を作成することができます。 後でプールにコンピューターを追加する準備ができたら、トポロジ ビルダーを再度実行して新しいプール メンバーを定義し、新しいトポロジを発行し、Skype for Business Server 展開ウィザードを使用して新しいディレクター プール メンバーをセットアップする必要があります。 また、プールの該当するロード バランサー (DNS 負荷分散またはロード バランサー機器) に新しいプール メンバーを追加する必要があります。 多くの場合、両方の負荷分散システムを使用します。 両方に新しいメンバー サーバーを追加していることを確認してください。 
  

