---
title: 信頼済みアプリケーション プールの FQDN を追加する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。
ms.openlocfilehash: 94cf0f611d754dc614111add734bf231c92c5a81
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217008"
---
# <a name="add-trusted-application-pool-fqdn"></a>信頼済みアプリケーション プールの FQDN を追加する
 
信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。
  
信頼済みアプリケーションをホストするサーバーまたはサーバー プールの FQDN。
  
負荷分散や高可用性のために信頼済みアプリケーションのサーバー プールを展開する場合は、[**複数コンピューターのプール**] を選択します。負荷分散や高可用性が必要ない場合は、[**単一コンピューターのプール**] を選択します。
  
> [!IMPORTANT]
> 信頼済みアプリケーションの単一サーバーを後でサーバー プールには変換できません。今後プールが必要になる可能性がある場合は、現状では単一のコンピューターのみ含まれる複数サーバー プールを展開し、必要に応じてサーバーを追加できます。 
  
信頼済みアプリケーション プールの詳細については、「[New-CsTrustedApplicationPool](https://docs.microsoft.com/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)」を参照してください。
  

