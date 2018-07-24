---
title: ビジネス サーバーのデータベースを Skype での AlwaysOn 可用性グループに追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: ビジネス サーバーのビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法を説明します。'
ms.openlocfilehash: f055466788494f10575b7bd3710705a138c456b2
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20976325"
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server"></a>ビジネス サーバーのデータベースを Skype での AlwaysOn 可用性グループに追加します。
 
**の概要:** Business Server のビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法について説明します。
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>AlwaysOn 可用性グループにデータベースを追加します。

1. SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。 フェールオーバー、プライマリ レプリカにします。
    
2. トポロジ ビルダーでは、AlwaysOn 可用性グループの SQL Server の FQDN をそのグループのプライマリ ノードの FQDN に設定します。
    
  - トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して **[ok]** をクリックします。
    
  - [Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。 新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。
    
  - **SQL Server の FQDN** ] ボックスで、ページの下部に、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。
    
3. トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。
    
4. AlwaysOn 可用性グループに新しいデータベースを追加するのにには、SQL Server Management Studio を使用します。
    

