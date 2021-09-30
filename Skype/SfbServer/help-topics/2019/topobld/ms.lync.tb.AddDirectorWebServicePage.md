---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
ROBOTS: NOINDEX, NOFOLLOW
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がである場合、ベース URL は `https://pool01.contoso.net` `pool01.contoso.net` .
ms.openlocfilehash: a47149d9d4f0dfb3fed08d9727aae3803c585834
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012921"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がである場合、ベース URL は `https://pool01.contoso.net` `pool01.contoso.net` .
  
単一のディレクターのみを展開する場合は、内部 Web サービス プールの完全修飾ドメイン名 (FQDN) を上書きできません。 ディレクターのプールに対してドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL (プール FQDN とは異なる必要があります。内部など) を指定できます。 \<your base URL\>
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。 たとえば、内部ドメインは 、 `contoso.net` ですが、外部ドメイン名は `contoso.com` . を使用して外部ベース URL を定義します `contoso.com domain name` 。 これは、エッジ展開でのリバース プロキシ サーバーで重要になります。 外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 
  

