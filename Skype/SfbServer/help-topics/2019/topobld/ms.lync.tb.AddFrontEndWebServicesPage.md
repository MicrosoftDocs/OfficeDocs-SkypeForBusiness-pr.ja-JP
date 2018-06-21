---
title: フロント エンド Web サービスを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
ms.openlocfilehash: 4858f64d98b917876ec8d03b4dca9f9d0fee512d
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/20/2018
ms.locfileid: "19972352"
---
# <a name="add-front-end-web-services"></a>フロント エンド Web サービスを追加します。
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL は、 https://pool01.contoso.net、ベース URL は、pool01.contoso.net です。
  
内部 Web サービス プール完全修飾ドメイン名 (FQDN) Standard Edition サーバーではオーバーライドできません。 ドメイン ネーム システム (DNS) の負荷分散、エンタープライズ エディションのフロント エンド プールを構成する場合は、異なる内部ベース URL が、プールの FQDN とは異なる必要がありますを指定できます (たとえば、内部の\<、ベース URL\>)。
  
異なる外部ベース URL を指定する名前付け規則を区別するために、内部のベース URL から。 内部ドメインには、contoso.net、ですが、外部ドメイン名は、contoso.com などです。 Contoso.com ドメイン名を使用して外部ベース URL を定義します。 これは、エッジの展開のリバース プロキシ サーバーには重要です。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じにする必要があります。 インスタント メッセージングとプレゼンスのフロント エンド プールへの HTTP アクセスが必要です。
  

