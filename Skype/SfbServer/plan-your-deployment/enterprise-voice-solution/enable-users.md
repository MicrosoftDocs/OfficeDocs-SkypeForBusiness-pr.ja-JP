---
title: E9-1-1 でユーザーを有効Skype for Business Server
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
description: Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、ローミング ユーザーをサポートする方法など)。
ms.openlocfilehash: b848359cb6a4324ab93804718d9416074f2af942c236d71c7b8e0de6abac4c05
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54328012"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>E9-1-1 でユーザーを有効Skype for Business Server
 
Skype for Business Server エンタープライズ VoIP での E9-1-1 展開の場所ポリシーに必要な決定(有効にするユーザー、ローミング ユーザーをサポートする方法など)。
  
クライアント登録中に、Skype for Business Serverは場所ポリシーを使用して、ユーザーが有効なユーザーの E9-1-1 プロパティエンタープライズ VoIP構成します。 このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 たとえば、場所ポリシーには、緊急ダイヤル文字列などの情報や、位置情報サービスが自動的に提供しない場合に、ユーザーが手動で場所を入力する必要があるかどうかなどの情報が含まれます。 場所ポリシーの完全な定義については、「場所ポリシーを計画する」を参照[Skype for Business Server。](location-policies.md)
  
Skype for Business Server、サブネットに基づくクライアント、またはグローバル ポリシー、サイト単位、またはユーザー単位のポリシーに基づくユーザーに場所ポリシーを割り当てできます。 ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。
  
 **すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**
  
> グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。 ただし、場所ポリシーを Skype for Business Server ネットワーク サイトに割り当て、サブネットをサイトに追加することで、E9-1-1 のサポートを企業内の選択した場所に制限し、サイトごとに E9-1-1 ルーティング動作を指定できます。 
    
 **ユーザー ポリシーを使用して個々のユーザーを有効にするか。**
  
> E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。
    
 **クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**
  
> ユーザーにグローバル、サイト、またはユーザーごとの場所ポリシーが割り当てられている場合は、クライアントが定義されたサブネット内に位置しないか、位置情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。 詳細については、「手動で場所[を取得](manually-acquiring-a-location.md)するためのユーザー エクスペリエンスを定義する」を参照Skype for Business Server。
    

