---
title: フロント エンドの Web サービスの追加 (2010)
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndWebServicesPage2010
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 97420584-3c2e-4d6d-9a2b-f7e361f1e2d1
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web `https://pool01.contoso.net`サービスの完全な URL がである場合、ベース URL は .`pool01.contoso.net`
ms.openlocfilehash: 5a4de05a5cf8c46c8c61a8b5bb54c4ebe9335f35
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399131"
---
# <a name="add-front-end-web-services-2010"></a>フロント エンドの Web サービスの追加 (2010)
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web `https://pool01.contoso.net`サービスの完全な URL がである場合、ベース URL は .`pool01.contoso.net`
  
サーバーの内部 Web サービス プールの完全修飾ドメイン名 (FQDN) をStandard Editionできません。 Enterprise Edition フロントエンド プールのドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL を指定できます (これは、プール FQDN\<your base URL\> とは異なる必要があります。内部など)。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。 たとえば、内部ドメインは 、 `contoso.net`ですが、外部ドメイン名は `contoso.com`. ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。 これは、エッジ展開でのリバース プロキシ サーバーで重要になります。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 インスタント メッセージングとプレゼンスでは、フロントエンド プールへの HTTP アクセスが必要です。
  

