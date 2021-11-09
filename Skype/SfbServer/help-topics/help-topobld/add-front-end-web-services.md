---
title: フロントエンドの Web サービスを追加する
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 99626970-1613-41ca-a36e-24bed1f459d7
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がである場合、ベース URL は `https://pool01.contoso.net` `pool01.contoso.net` .
ms.openlocfilehash: d8ff2267eba5a7d52a41e5d1ed2c937338972588
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853131"
---
# <a name="add-front-end-web-services"></a>フロント エンドの Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がである場合、ベース URL は `https://pool01.contoso.net` `pool01.contoso.net` .
  
サーバーの内部 Web サービス プールの完全修飾ドメイン名 (FQDN) をStandard Editionできません。 Enterprise Edition フロントエンド プールのドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL を指定できます。これは、プール FQDN (internal- など) とは異なる必要があります \<your base URL\> 。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。 たとえば、内部ドメインは 、 `contoso.net` ですが、外部ドメイン名は `contoso.com` . ドメイン名を使用して外部ベース URL を `contoso.com` 定義します。 これは、エッジ展開でのリバース プロキシ サーバーで重要になります。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 インスタント メッセージングとプレゼンスでは、フロントエンド プールへの HTTP アクセスが必要です。
  

