---
title: 証明書のリスト
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: 証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。 続行するには、[次へ] をクリックします。
ms.openlocfilehash: 0f7f6b3fc0801a71f8390f82396c2b4711d4295e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764295"
---
# <a name="certificate-list"></a>証明書のリスト
 
証明書を割り当てるには、ローカル証明書ストアから証明書を選択します。 **[次へ]** をクリックして続行します。
  
[**ローカル証明書ストアから証明書を選びます**] ウィンドウに選択対象として表示される証明書は、必要な証明書使用法に割り当てることができる有効な証明書です。選択する証明書が正しい証明書かどうかは、[**証明書の詳細の表示**] をクリックすることによって確認できます。[**詳細**] タブでは、その証明書で構成されているサブジェクト名とサブジェクトの別名の指定を確認できます。
  
> [!IMPORTANT]
> 選択ウィンドウの一覧に証明書が何も表示されない可能性もあります。そのような場合の一般的な原因は、信頼されたルート証明書または中間証明機関の証明書が目的のサーバーにインストールされていないことにより、証明書を検証できず、したがって証明書によって作成された証明機関までの信頼チェーンを保持できないことです。この問題を解決するには、ルート証明機関 (CA) 証明書、すべての中間 CA 証明書、および発行 CA 証明書を通常含んでいる、証明書チェーンを要求してインポートします。 
  

