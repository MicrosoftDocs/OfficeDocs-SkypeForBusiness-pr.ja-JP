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
- CSH
ms.custom:
- ms.lync.tb.AddDirectorWebServicePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3ed3bdde-c3b5-4fe9-a96b-37099cbd6234
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
ms.openlocfilehash: 5d965eb591afca8d7154d8fd12af741ddaf65084
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219468"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL がの場合、 https://pool01.contoso.net ベース url は pool01.contoso.net になります。
  
1つのディレクターのみを展開する場合は、内部 Web サービスプールの完全修飾ドメイン名 (FQDN) を無効にすることはできません。 ディレクタープールのドメインネームシステム (DNS) 負荷分散を構成している場合は、別の内部ベース URL を指定できます (プールの FQDN とは異なる必要があり、たとえば内部-など \<your base URL\> )。
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 
  

