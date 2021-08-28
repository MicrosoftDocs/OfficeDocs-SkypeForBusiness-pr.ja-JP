---
title: 証明書要求 (証明機関)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
ROBOTS: NOINDEX, NOFOLLOW
description: '[証明機関 (CA) の選択] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う際に、次の 2 つのオプションが表示されます。'
ms.openlocfilehash: 96f601a26f64802e93d776438dfc92b50f3ae76a
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/26/2021
ms.locfileid: "58591831"
---
# <a name="certificate-request-certificate-authority"></a>証明書要求 (証明機関)
 
[**証明機関 (CA) の選択**] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う際に、次の 2 つのオプションが表示されます。
  
1. 環境で検出された一覧から CA を選択する。
    
2. 別の証明機関を指定する。
    
最初のオプションを選択すると、環境で検出された Windows Server ベースの証明機関すべてが含まれるドロップダウン リストが表示されます。 証明書に適切な証明機関を選択します。 どの CA を選択するのかを把握するために、CA 管理者に問い合わせることが必要になる場合があります。
  
2 番目のオプションを選択した場合、証明書に使用する証明機関の完全修飾ドメイン名 (FQDN) および CA インスタンスを入力します。このオプションは、使用する CA が Windows Server ベースの CA ではないが、Windows Server ベースの CA でも機能する場合に適しています。
  
> [!IMPORTANT]
> 証明書要求を適切に行うために必要なグループ メンバーシップを確認します。 通常、証明機関には、サーバーにサーバーをインストールするための要件とは異なるSkype for Business Serverがあります。 証明書を要求するための要件について、CA 管理者に確認します。 
  

