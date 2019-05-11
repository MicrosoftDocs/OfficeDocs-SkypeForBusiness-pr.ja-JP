---
title: 信頼済みアプリケーション プールの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
ms.openlocfilehash: 11331569e7db06fba6d7dc99529fe83ad3fe2ddd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888969"
---
# <a name="add-trusted-application-pool-fqdn"></a>信頼済みアプリケーション プールの FQDN の追加
 
信頼されたアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
  
サーバーまたは信頼されたアプリケーションをホストするサーバー プールの FQDN です。
  
負荷分散と高可用性は、信頼されたアプリケーション サーバーのプールを展開する、または負荷分散や高可用性が必要ない場合は、 **1 台のコンピューターのプール**を選択する場合は、**複数コンピューターのプール**を選択します。
  
> [!IMPORTANT]
> 1 つの信頼されたアプリケーション サーバーは、後で、サーバーのプールに変換できません。 プールは、将来的にする必要がある場合は、ここで、1 台のコンピューターを含む複数のサーバー プールを展開し、必要なときにサーバーを追加できます。 
  
信頼されたアプリケーション プールに関する詳細情報は、[新規 CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)を参照してください。
  

