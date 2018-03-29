---
title: ビジネス サーバー 2015 の Skype での AlwaysOn 可用性グループにデータベースを追加します。
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/30/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 026c4469-f471-4e4f-a77d-a7d22a925e5a
description: '概要: ビジネス サーバー 2015 のビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法を説明します。'
ms.openlocfilehash: 31678d6cc374ecdbe40d2fdf3039905176c0178d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="add-databases-to-an-alwayson-availability-group-in-skype-for-business-server-2015"></a>ビジネス サーバー 2015 の Skype での AlwaysOn 可用性グループにデータベースを追加します。
 
**の概要:**ビジネス サーバー 2015 のビジネス サーバー データベースの複数の Skype を Skype で既存の AlwaysOn 可用性グループに追加する方法について説明します。
  
### <a name="adding-databases-to-an-alwayson-availability-group"></a>AlwaysOn 可用性グループにデータベースを追加します。

1. SQL Server Management Studio を開き AlwaysOn 可用性グループに移動します。 フェールオーバー、プライマリ レプリカにします。
    
2. トポロジ ビルダーでは、AlwaysOn 可用性グループの SQL Server の FQDN をそのグループのプライマリ ノードの FQDN に設定します。
    
  - トポロジ ビルダーを開き**既存の展開からトポロジをダウンロード**するを選択して**[ok]**をクリックします。
    
  - [Skype for Business Server]、使用するトポロジ、[**SQL Server ストア**] の順に展開します。 新しい AlwaysOn 可用性グループの SQL ストアを右クリックし、[**プロパティの編集**] をクリックします。
    
  - **SQL Server の FQDN** ] ボックスで、ページの下部に、AlwaysOn 可用性グループのプライマリ ノードの FQDN を入力します。
    
3. トポロジを公開します。[**操作**] メニューから、[**トポロジ**]、[**公開**] の順にクリックします。続いて確認ページで [**次へ**] をクリックします。
    
4. AlwaysOn 可用性グループに新しいデータベースを追加するのにには、SQL Server Management Studio を使用します。
    

