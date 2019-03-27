---
title: 証明書要求 (証明機関)
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: '[証明機関 (CA) を選択してください] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う場合、次の 2 つのオプションが表示されます。'
ms.openlocfilehash: 5681f570a6c418263545386afecfe4b7329bc45c
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30880194"
---
# <a name="certificate-request-certificate-authority"></a>証明書要求 (証明機関)
 
[**証明機関 (CA) を選択してください**] ページでオンライン証明機関 (CA) (通常、内部ネットワーク上のサーバー) に対して証明書要求を行う場合、次の 2 つのオプションが表示されます。
  
1. 環境で検出された一覧から CA を選択する。
    
2. 別の証明機関を指定する。
    
最初のオプションを選択する場合は、環境内で検出されたすべての Windows サーバー ベースの証明機関を含むドロップダウン リストが表示されます。 証明書に適切な証明機関を選択します。 どの CA を選択するかについて、CA 管理者への問い合わせが必要になる場合があります。
  
2 番目のオプションを選択した場合、証明書に使用する証明機関の完全修飾ドメイン名 (FQDN) および CA インスタンスを入力します。このオプションは、使用する CA が Windows Server ベースの CA ではないが、Windows Server ベースの CA でも機能する場合に適しています。
  
> [!IMPORTANT]
> 証明書要求を適切に行うために必要なグループ メンバーシップを確認します。 通常、証明機関では、Skype をビジネスのサーバーのサーバーにインストールする必要条件から別のアクセス権が必要があります。 証明書を要求するための要件について、CA 管理者に確認します。 
  

