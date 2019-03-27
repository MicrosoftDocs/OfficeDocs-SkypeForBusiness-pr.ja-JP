---
title: フロントエンドの Web サービスの追加
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 20687fd74c90e6394d02ddeb2f6f37f6e4746e53
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30888966"
---
# <a name="add-front-end-web-services"></a>フロントエンドの Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
  
内部 Web サービス プール完全修飾ドメイン名 (FQDN) Standard Edition サーバーではオーバーライドできません。 ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、異なる内部ベース URL が、プールの FQDN とは異なる必要がありますを指定できます (たとえば、内部の\<、ベース URL\>)。
  
異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。 内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。 Contoso.com ドメイン名を使用して外部ベース URL を定義します。 これは、エッジの展開のリバース プロキシ サーバーには重要です。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。 インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。
  

