---
title: Skype for Business Server でユーザーの E9-1 を有効にする
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 有効にするユーザー、およびローミングユーザーをサポートする方法など、Skype for Business Server エンタープライズボイスの E9 展開の場所ポリシーに必要な決定。
ms.openlocfilehash: 717b127a94fbac966476c681cfb7f6e81d91bde9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802957"
---
# <a name="enable-users-for-e9-1-1-in-skype-for-business-server"></a>Skype for Business Server でユーザーの E9-1 を有効にする
 
有効にするユーザー、およびローミングユーザーをサポートする方法など、Skype for Business Server エンタープライズボイスの E9 展開の場所ポリシーに必要な決定。
  
顧客の登録中に、Skype for Business Server は位置情報ポリシーを使って、エンタープライズボイス対応ユーザーの E9 プロパティを構成します。 このポリシーには、E9-1-1 の実装方法を定義する設定が含まれます。 たとえば、場所情報のポリシーには、緊急ダイヤルの文字列などの情報が含まれています。また、位置情報サービスで自動的に場所を指定しない場合は、その場所を手動で入力する必要があります。 位置情報ポリシーの完全な定義については、「 [Skype For Business Server の位置情報ポリシーの計画](location-policies.md)」を参照してください。
  
Skype for Business Server は、サブネットに基づいてクライアントまたはグローバル、サイトごと、またはユーザーごとのポリシーに基づいてユーザーに位置情報ポリシーを割り当てることができます。 ユーザーを有効にする方法を決定するには、まず、次の情報を確認する必要があります。
  
 **すべてのユーザーを有効にするか、またはエンタープライズの特定の地理的領域にサポートを限定するか。**
  
> グローバルな場所ポリシーを使用することで、エンタープライズ内のすべてのユーザーに場所を割り当てることができます。 ただし、Skype for Business Server ネットワークサイトに位置情報ポリシーを割り当て、サブネットをサイトに追加することによって、E9 のサポートをエンタープライズ内の選択した場所に対して制限することができます。また、サイトごとに E9 のルーティング動作を指定することもできます。 
    
 **ユーザー ポリシーを使用して個々のユーザーを有効にするか。**
  
> E9-1-1 サポートをカスタマイズする必要がある場合は、場所ポリシーを特定のユーザーまたは共通領域電話の連絡先オブジェクトに直接割り当てることができます。
    
 **クライアントがネットワーク外を移動している場合、または定義されていないサブネットから接続されている場合、そのクライアントでも E9-1-1 を有効にするか。**
  
> ユーザーにグローバル、サイト、またはユーザーごとの場所のポリシーが割り当てられている場合、クライアントが定義されたサブネット内に存在しない場合、または場所情報サービスによって場所が見つからない場合は、クライアントに場所を手動で入力する必要があります。 詳細については、「 [Skype For Business Server で場所を手動で取得するためのユーザーエクスペリエンスの定義](manually-acquiring-a-location.md)」を参照してください。
    

