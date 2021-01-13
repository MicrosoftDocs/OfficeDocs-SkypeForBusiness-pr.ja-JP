---
title: Skype for Business Server で E9-1-1 のユーザーを有効にする
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3cc64f5b-492e-4c47-9713-3c376f2aad02
description: Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、移動ユーザーをサポートする方法など)。
ms.openlocfilehash: 9a2ced694357b9225555a05c10e93a1006a771b4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825747"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Skype for Business Server で E9-1-1 のユーザーを有効にする
 
Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、移動ユーザーをサポートする方法など)。
  
クライアントの登録時に、Skype for Business Server は場所ポリシーを使用して、ユーザーが有効なユーザーの E9-1-1 エンタープライズ VoIPを構成します。 このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 たとえば、場所のポリシーには、緊急ダイヤル文字列などの情報や、場所情報サービスが自動的に提供しない場合に、ユーザーが場所を手動で入力する必要があるかどうかなどの情報が含まれます。 場所ポリシーの完全な定義については、「Skype for Business Server の場所 [ポリシーを計画する」を参照してください](location-policies.md)。
  
Skype for Business Server は、場所ポリシーをサブネットに基づいてクライアントに割り当てるか、グローバル ポリシー、サイト単位、またはユーザー単位のポリシーに基づいてユーザーに割り当てできます。 ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。
  
 **すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**
  
> グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。 ただし、場所ポリシーを Skype for Business Server ネットワーク サイトに割り当て、サブネットをサイトに追加することで、E9-1-1 のサポートを企業内の選択した場所に制限し、サイトごとに E9-1-1 ルーティング動作を指定できます。 
    
 **ユーザー ポリシーを使用して個々のユーザーを有効にするか。**
  
> E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。
    
 **クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**
  
> ユーザーにグローバル、サイト、またはユーザー単位の場所ポリシーが割り当てられている場合、クライアントが定義されたサブネット内にない場合や、場所情報サービスによって場所が見つからない場合は、ユーザーにクライアントに場所を手動で入力する必要があります。 詳細については、「Skype for Business Server で場所を手動で取得するためのユーザー エクスペリエンスの定義 [」を参照してください](manually-acquiring-a-location.md)。
    

