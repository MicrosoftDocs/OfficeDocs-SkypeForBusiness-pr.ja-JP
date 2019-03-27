---
title: ビジネス用の Skype のコール パークの正規化ルールを確認します。
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: deaa170f-041e-45cb-8eab-f02931ab541e
description: ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。
ms.openlocfilehash: 794d64efcefbc4b36fac84e6356df46df76dc5a2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877277"
---
# <a name="verify-normalization-rules-for-call-park-in-skype-for-business"></a>ビジネス用の Skype のコール パークの正規化ルールを確認します。
 
ビジネス サーバーのエンタープライズ VoIP は、Skype のコール パークの正規化規則について説明します。
  
パーク軌道を正規化する必要がありますはありません。 ダイヤル プランでオービット番号が正規化されていないことを確認してください。 軌道が正規化されていることを防ぐため、追加の正規化ルールを作成する必要がある場合の手順を[を作成するビジネス サーバーの Skype のダイヤル プランを変更または](dial-plans.md)ため、新しい正規化ルールを定義するのにはその**パターンに一致するには**軌道範囲を識別**変換パターン**は、 **$1**とします。 などの場合、コール パークの移動範囲は 7000-7999 の場合、**一致させるパターン**は、 **^(7\d{3})$** **$1**で、**翻訳のパターン**です。
  
> [!IMPORTANT]
> ダイヤル プランの既定正規化ルールが含まれていないかどうかを必ず **^(\d\*)**。 それ以外の場合、コール パーク正規化ルールは実行されません。
  
## <a name="see-also"></a>関連項目

[作成またはビジネス サーバーの Skype のダイヤル プランを変更します。](dial-plans.md)

