---
title: 証明書の要求、インストール、または割り当て
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: '手順 3: [実行] をクリックすると、証明書の要求、インストール、または割り当てによって証明書ウィザードが開始されます。 ウィザードを介して構成される証明書は、トポロジ ビルダーによって構成され、サーバーの全体管理ストアに発行される Skype for Business Server トポロジの定義に基づいて行います。 組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。 コンピューターと CA が存在するドメイン内の認証済みドメイン ユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定できます。'
ms.openlocfilehash: d6a4a784e96f17a62297d248c2723702569b5b45
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60863034"
---
# <a name="request-install-or-assign-certificates"></a>証明書の要求、インストール、または割り当て
 
 **手順 3: [実行] をクリック** すると、証明書の要求、インストール、または割り当てによって証明書ウィザードが **起動します**。 ウィザードを介して構成される証明書は、トポロジ ビルダーによって構成され、サーバーの全体管理ストアに発行される Skype for Business Server トポロジの定義に基づいて行います。 組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。 コンピューターと CA が存在するドメイン内の認証済みドメイン ユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定できます。
  
> [!NOTE]
> また、証明書ウィザードを使用して、パブリック CA や他のオフライン公開キー基盤 (PKI) に送信されるオフライン証明書要求を要求して処理することはできません。コンピューターへのログオンで必要なメンバーシップ以外に、オフライン要求を生成するために必要な特定のグループ メンバーシップはありません。パブリック CA の応答を処理し、証明書をコンピューターと役割に割り当てるには、ローカル管理者グループのメンバーかそれと同等のユーザーとしてログオンする必要があります。 
  

