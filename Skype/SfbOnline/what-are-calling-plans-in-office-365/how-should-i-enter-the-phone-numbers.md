---
title: 電話番号を入力する方法必要がありますか。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Skype ビジネスのためにそれらを移植するときに、電話番号を設定する方法について説明します。 '
ms.openlocfilehash: 68fe698612c095e657dab56723df7de6eb13b858
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/03/2018
---
# <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法必要がありますか。

電話番号を移植するときに正しい形式で入力してください。 
  
> [!NOTE]
> 各電話番号や電話番号の範囲は、行ごとに別々 に入力する必要があります。 
  
- 1 つの電話番号を入力します。
    
  - すべての特殊文字は無視されます (ダッシュを含む「-」)。 例:
    
  - 10 桁の番号の: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649** **+14255550649**に修正されます。
    
  - 11 桁の数: **1\*() (\*&amp;42&amp;\*() (\*&amp;55550649** **+14255550649**に修正されます。
    
  - 10 または 11 桁の数字がある場合、すべてのタグは無視されます。 たとえば、 ** \<div > 4255551234\</div >** **+14255551234**になります。
    
  - "-"、スペースとかっこは無視されます。 例:
    
  - 10 桁の番号: **(425) 555-6776**を**+14255556776**に修正されます。
    
  - 11 桁の数: **555-6776 の 1(425)**を**+14255556776**に修正されます。
    
  - すべての文字は特殊文字として扱われ、10 桁または 11 桁の電話番号がある場合は無視します。 例:
    
  - 10 桁の番号: **14jaosia2reoij05jof55506ajfoj49isdjf**を**+14255550649**に修正されます。
    
  - 11 桁の数: **1ade4jaoda2rfoij05ojof55506dsfoj49if**を**+14255550649**に修正されます。
    
  - 他の言語であっても、特殊文字の任意の組み合わせが修正されます。 例: 
    
  - 10 桁の番号:**中文4中文2ajj5\*() (\*(5().551345** **+14555551345**に修正されます。
    
  - 11 桁の数:**中文4中文2$ a5\*() (\*(5().55 (.1345** **+14555551345**に修正されます。
    
  - 任意の数値には、10 桁または 11 以上の数字が含まれている、ユーザーを修正するためにハイライトされます。
    
  - \*\*5551245\* \*がハイライトされ、修正する必要があります。
    
  - **1234567891011**がハイライトされ、修正する必要があります。
    
  - 10 桁または 11 以上の数字、特殊文字、任意の数値が自動的に修正されることがなくハイライトされます。
    
  - 入力される特殊文字なしの 7 桁の番号: 文字を無視しないが**123456abcdefg7**が強調表示され、修正する必要があります。
    
  - 入力される特殊文字と 7 桁の番号: **12345!@#$%^&amp;\*()--@# $% ^&amp;\*() 7**を修正するが強調表示されます。 特殊文字は無視されません。
    
- 電話番号の範囲を入力します。
    
  - 2 つの電話番号を使用できます。 少ない数の範囲の最初の数値でなければなりません。
    
  - すべての特殊文字 (ハイフンを除く"-") は 1 つの数値として扱われ、同じ。 たとえば、 **(425) 555 0&amp;\*(123-(1425) 5557899nm**に修正されます。 **+14255550123 - +13202040659**。
    
  - "-"のみ 2 つの数値を区切るために使用します。 複数を含めることはサポートされていません"、"番号の範囲の。 として**(425) 555-0649 ・ (425) 555-1115**を入力するたとえば、 **(425) 5550649-(425) 5551115**。
    
 **完全な手順については、 [Office 365 に電話番号を転送する](transfer-phone-numbers-to-office-365.md)を参照してください。**

 > [!NOTE]
> 無料電話番号

  
## <a name="related-topics"></a>[米国 (無料の電話番号) 用の承認状 (LOA) (v.2.0)](http://download.microsoft.com/download/F/0/1/F01AE714-0F3C-4D9D-B41A-DFD180EC1622/Letter of Authorization %28LOA%29 for the U.S. (Toll Free numbers) (v.3.1) (en-US).pdf)
電話番号の管理フォームのダウンロード

[通話プランで使用されるさまざまな種類の電話番号](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[[Skype for Business 新しい電話番号の申請](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。

[緊急通話の利用条件](emergency-calling-terms-and-conditions.md)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://go.microsoft.com/fwlink/?LinkID=692099)

  
 