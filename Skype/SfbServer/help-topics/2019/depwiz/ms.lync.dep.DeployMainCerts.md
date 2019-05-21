---
title: 証明書の要求、インストール、または割り当て
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: '手順 3: [実行] をクリックすると、証明書ウィザードが開始されます。 ウィザードを使用して構成された証明書は、構成され、トポロジビルダーが中央管理ストアに公開した Skype for Business Server トポロジの定義に基づいています。 組織内のオンライン証明機関 (CA) に対して証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンしている必要があります。 また、コンピューターと CA が存在するドメインで、認証されたドメインユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定することができます。'
ms.openlocfilehash: faf6fa63770d27c90a94c01753d99a079cb5ef28
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299012"
---
# <a name="request-install-or-assign-certificates"></a>証明書の要求、インストール、または割り当て
 
 **手順 3:** [**実行**] をクリックすると、証明書ウィザードが開始されます。 ウィザードを使用して構成された証明書は、構成され、トポロジビルダーが中央管理ストアに公開した Skype for Business Server トポロジの定義に基づいています。 組織内のオンライン証明機関 (CA) に対して証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンしている必要があります。 また、コンピューターと CA が存在するドメインで、認証されたドメインユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定することができます。
  
> [!NOTE]
> また、証明書ウィザードを使用して、パブリック CA や他のオフライン公開キー基盤 (PKI) に送信されるオフライン証明書要求を要求して処理することはできません。コンピューターへのログオンで必要なメンバーシップ以外に、オフライン要求を生成するために必要な特定のグループ メンバーシップはありません。パブリック CA の応答を処理し、証明書をコンピューターと役割に割り当てるには、ローカルの Administrators グループのメンバーかそれと同等のユーザーとしてログオンする必要があります。 
  

