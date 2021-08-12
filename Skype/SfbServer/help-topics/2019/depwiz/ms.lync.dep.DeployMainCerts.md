---
title: 証明書の要求、インストール、または割り当て
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
ROBOTS: NOINDEX, NOFOLLOW
description: '手順 3: [実行] をクリックすると、証明書の要求、インストール、または割り当てによって証明書ウィザードが開始されます。 ウィザードを介して構成される証明書は、トポロジ ビルダーによって構成され、サーバーの全体管理ストアに発行される Skype for Business Server トポロジの定義に基づいて行います。 組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。 コンピューターと CA が存在するドメイン内の認証済みドメイン ユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定できます。'
ms.openlocfilehash: 44eb8c3ca1361742a114b3763bde911842734c1ced498dfae73c1f8a7c3c3d45
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54282180"
---
# <a name="request-install-or-assign-certificates"></a>証明書の要求、インストール、または割り当て
 
 **手順 3: [実行] をクリック** すると、証明書の要求、インストール、または割り当てによって証明書ウィザードが **起動します**。 ウィザードを介して構成される証明書は、トポロジ ビルダーによって構成され、サーバーの全体管理ストアに発行される Skype for Business Server トポロジの定義に基づいて行います。 組織内のオンライン証明機関 (CA) の証明書ウィザードを正常に実行するには、コンピューターのローカル管理者グループのメンバーであるユーザーとしてコンピューターにログオンする必要があります。 コンピューターと CA が存在するドメイン内の認証済みドメイン ユーザーである必要があります。 証明書ウィザードでは、組織の CA にアクセスするための代替資格情報を指定できます。
  
> [!NOTE]
> また、証明書ウィザードを使用して、パブリック CA や他のオフライン公開キー基盤 (PKI) に送信されるオフライン証明書要求を要求して処理することはできません。コンピューターへのログオンで必要なメンバーシップ以外に、オフライン要求を生成するために必要な特定のグループ メンバーシップはありません。パブリック CA の応答を処理し、証明書をコンピューターと役割に割り当てるには、ローカル管理者グループのメンバーかそれと同等のユーザーとしてログオンする必要があります。 
  

