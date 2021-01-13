---
title: ディレクター Web サービスの追加
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
ms.openlocfilehash: aa3c96a6a47a35ae8c65b0a7a6bcb5df696bada4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828897"
---
# <a name="add-director-web-service"></a>ディレクター Web サービスの追加
 
ベース URL は、https:// の部分を除いた URL の Web サービス ID です。 たとえば、プールの Web サービスの完全な URL が次の場合、ベース https://pool01.contoso.net URL はpool01.contoso.net。
  
1 つのディレクターのみを展開する場合は、内部 Web サービス プールの完全修飾ドメイン名 (FQDN) を上書きできません。 ディレクターのプールに対してドメイン ネーム システム (DNS) 負荷分散を構成する場合は、別の内部ベース URL (プールの FQDN とは異なる必要があります。内部 URL など) を指定できます。 \<your base URL\>
  
内部ベース URL とは異なる外部ベース URL を指定して、ドメイン名前付けを区別できます。たとえば、内部ドメインは contoso.net ですが、外部ドメイン名は contoso.com という場合があります。ドメイン名 contoso.com を使用して、外部ベース URL を定義しています。これは、エッジ展開でのリバース プロキシ サーバーで重要になります。外部ベース URL のドメイン名は、リバース プロキシの FQDN のドメイン名と同じである必要があります。 
  

