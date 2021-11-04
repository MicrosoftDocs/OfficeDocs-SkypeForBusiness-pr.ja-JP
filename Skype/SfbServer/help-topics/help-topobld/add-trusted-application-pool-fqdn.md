---
title: 信頼済みアプリケーション プールの FQDN を追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddExternalApplicationPoolPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 5d065268-a694-49a1-b285-9be80a09995c
description: 信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。
ms.openlocfilehash: 060a427c1921368573ca0c68dff73f9487ba3697
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758359"
---
# <a name="add-trusted-application-pool-fqdn"></a>信頼済みアプリケーション プールの FQDN の追加
 
信頼済みアプリケーション プールの完全修飾ドメイン名 (FQDN) を定義するには、次のものを指定します。
  
信頼済みアプリケーションをホストするサーバーまたはサーバー プールの FQDN。
  
負荷分散や高可用性のために信頼済みアプリケーションのサーバー プールを展開する場合は、[**複数コンピューターのプール**] を選択します。負荷分散や高可用性が必要ない場合は、[**単一コンピューターのプール**] を選択します。
  
> [!IMPORTANT]
> 信頼済みアプリケーションの単一サーバーを後でサーバー プールには変換できません。今後プールが必要になる可能性がある場合は、現状では単一のコンピューターのみ含まれる複数サーバー プールを展開し、必要に応じてサーバーを追加できます。 
  
信頼済みアプリケーション プールの詳細については、「[New-CsTrustedApplicationPool](/powershell/module/skype/new-cstrustedapplicationpool?view=skype-ps)」を参照してください。
