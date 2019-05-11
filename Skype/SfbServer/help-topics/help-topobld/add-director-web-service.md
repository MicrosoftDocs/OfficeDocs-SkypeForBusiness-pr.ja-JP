---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 8fac9baf89f36dd90d0e98e235b6c8b297672616
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886544"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
  
単一のディレクターを展開する場合は、内部の Web サービス プール完全修飾ドメイン名 (FQDN) をオーバーライドできません。 内部の別のベース URL を指定するには、ドメイン ネーム システム (DNS) の負荷分散ディレクターのプールを構成する場合 (とプールの FQDN とは異なる必要があります可能性があります、たとえば、内部の\<、ベース URL\>)。
  
異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。 内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。 Contoso.com ドメイン名を使用して外部ベース URL を定義します。 これは、エッジの展開のリバース プロキシ サーバーには重要です。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。 
  

