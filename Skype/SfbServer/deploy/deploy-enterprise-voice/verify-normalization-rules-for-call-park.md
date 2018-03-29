---
title: Skype for Business 2015 でのコール パーク正規化ルールの確認
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。
ms.openlocfilehash: 4f3651394bbdb5556a83aa34739a86f8d06f1396
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business-2015"></a>Skype for Business 2015 でのコール パーク正規化ルールの確認
 
ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。
  
パーク軌道を正規化する必要がありますはありません。 ダイヤル プランでオービット番号が正規化されていないことを確認してください。 軌道が正規化されていることを防ぐため、追加の正規化ルールを作成する必要がある場合の手順を[を作成するビジネス サーバー 2015 の Skype のダイヤル プランを変更するまたは](dial-plans.md)ため、新しい正規化ルールを定義するのにはその**パターンに一致するには**軌道範囲を識別**変換パターン**は、 **$1**とします。 などの場合、コール パークの移動範囲は 7000-7999 の場合、**一致させるパターン**は、 **^ (7\d {3}) $** **$1**で、**翻訳のパターン**です。
  
> [!IMPORTANT]
> ダイヤル プランの既定正規化ルールが含まれていないかどうかを必ず**^(\d\*)**。 それ以外の場合、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

#### 

[作成またはビジネス サーバー 2015 の Skype のダイヤル プランを変更します。](dial-plans.md)

