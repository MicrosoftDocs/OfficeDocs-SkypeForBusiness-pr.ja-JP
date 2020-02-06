---
title: 証明書要求 (証明機関)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: '[証明機関 (CA) を選択してください] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う場合、次の 2 つのオプションが表示されます。'
ms.openlocfilehash: 6c52a46bf40211d05ea47205d2573627910d3ba6
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796758"
---
# <a name="certificate-request-certificate-authority"></a>証明書要求 (証明機関)
 
[**証明機関 (CA) を選択してください**] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う場合、次の 2 つのオプションが表示されます。
  
1. 環境で検出された一覧から CA を選択する。
    
2. 別の証明機関を指定する。
    
最初のオプションを選択すると、環境で検出されたすべての Windows Server ベースの証明機関を含むドロップダウンリストが表示されます。 証明書に適切な証明機関を選択します。 どの CA を選択するかについて、CA 管理者への問い合わせが必要になる場合があります。
  
2 番目のオプションを選択した場合、証明書に使用する証明機関の完全修飾ドメイン名 (FQDN) および CA インスタンスを入力します。このオプションは、使用する CA が Windows Server ベースの CA ではないが、Windows Server ベースの CA でも機能する場合に適しています。
  
> [!IMPORTANT]
> 証明書要求を適切に行うために必要なグループ メンバーシップを確認します。 通常、証明機関には、サーバーに Skype for Business Server をインストールするための要件に対するさまざまなアクセス許可の要件があります。 証明書を要求するための要件について、CA 管理者に確認します。 
  

