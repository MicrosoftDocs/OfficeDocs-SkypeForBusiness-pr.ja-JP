---
title: フロント エンド Web サービス 2010 を追加します。
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 5d5c935d1357c2baf66ed17ab762db8fd442ac67
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19976894"
---
# <a name="add-front-end-web-services-2010"></a>フロント エンド Web サービス 2010 を追加します。
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
  
内部 Web サービス プール完全修飾ドメイン名 (FQDN) を Standard Edition Server を上書きすることはできません。 ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、内部の別の基本 URL を指定できます (プールの FQDN とは異なる必要があり、可能性があります、たとえば、内部の\<、ベース URL\>)。
  
異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。 内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。 Contoso.com ドメイン名を使用して外部ベース URL を定義します。 これは、エッジの展開のリバース プロキシ サーバーには重要です。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。 インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。
  

