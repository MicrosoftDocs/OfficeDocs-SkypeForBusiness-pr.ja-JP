---
title: 信頼済みアプリケーション プールの FQDN の追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
ROBOTS: NOINDEX, NOFOLLOW
description: 信頼できるアプリケーションプールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
ms.openlocfilehash: 026994a57da7838b2799484f000d69d8c9a168d7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278462"
---
# <a name="add-trusted-application-pool-fqdn"></a>信頼済みアプリケーション プールの FQDN の追加
 
信頼できるアプリケーションプールの完全修飾ドメイン名 (FQDN) を定義するには、次のように指定します。
  
信頼されたアプリケーションをホストするサーバーの FQDN。
  
信頼されたアプリケーション用のサーバープールをロードバランシングおよび高可用性から展開する場合は、[**複数のコンピュータープール**] を選びます。また、負荷分散や高可用性を必要としない場合は、[**単一コンピュータープール**] を選びます。
  
> [!IMPORTANT]
> 1つの信頼済みアプリケーションサーバーを、後でサーバーのプールに変換することはできません。 今後はプールが必要になる可能性があると考えられる場合は、1台のコンピューターを含む複数のサーバープールを現在展開し、必要に応じてサーバーを追加します。 
  
信頼されたアプリケーションのプールの詳細については、「 [New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)」を参照してください。
  

