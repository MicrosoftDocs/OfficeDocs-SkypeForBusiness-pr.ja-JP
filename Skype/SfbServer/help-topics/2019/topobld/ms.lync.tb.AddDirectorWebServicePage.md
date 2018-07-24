---
title: ディレクター Web サービスを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 2350a728580d89e5ff1e18106c558ec817ab2f37
ms.sourcegitcommit: 1f7299f535ec6b34f92301b4abc14d8922492eeb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "21061807"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスを追加します。
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
  
単一のディレクターを展開する場合は、内部の Web サービス プール完全修飾ドメイン名 (FQDN) をオーバーライドできません。 内部の別のベース URL を指定するには、ドメイン ネーム システム (DNS) の負荷分散ディレクターのプールを構成する場合 (とプールの FQDN とは異なる必要があります可能性があります、たとえば、内部の\<、ベース URL\>)。
  
異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。 内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。 Contoso.com ドメイン名を使用して外部ベース URL を定義します。 これは、エッジの展開のリバース プロキシ サーバーには重要です。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。 
  

