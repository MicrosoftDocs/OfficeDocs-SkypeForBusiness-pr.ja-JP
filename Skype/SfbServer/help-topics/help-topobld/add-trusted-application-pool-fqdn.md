---
title: 信頼済みアプリケーション プールの FQDN の追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
ms.openlocfilehash: b10053abdb8abcb11aa1a69e1acfcb97a92c4a76
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879970"
---
# <a name="add-trusted-application-pool-fqdn"></a>信頼済みアプリケーション プールの FQDN の追加
 
信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
  
サーバーまたは信頼されたアプリケーションをホストするサーバー プールの FQDN です。
  
負荷分散と高可用性は、信頼されたアプリケーション サーバーのプールを展開する、または負荷分散や高可用性が必要ない場合は、 **1 台のコンピューターのプール**を選択する場合は、**複数コンピューターのプール**を選択します。
  
> [!IMPORTANT]
> 1 つの信頼されたアプリケーション サーバーは、後で、サーバーのプールに変換できません。 プールは、将来的にする必要がある場合は、ここで、1 台のコンピューターを含む複数のサーバー プールを展開し、必要なときにサーバーを追加できます。 
  
信頼されたアプリケーション プールに関する詳細情報は、[新規 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)を参照してください。
  

