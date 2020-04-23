---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 0cdec8e371d7803bdcac781209b0fd9e55cb82be
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821179"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がhttps://pool01.contoso.netの場合、ベース url は pool01.contoso.net になります。
  
1つのディレクターのみを展開する場合は、内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を無効にすることはできません。 ディレクタープールのドメインネームシステム (DNS) 負荷分散を構成している場合は、別の内部ベース URL を指定できます (プールの FQDN と\<は異なる必要があり、ベース url\>など)。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 
  

