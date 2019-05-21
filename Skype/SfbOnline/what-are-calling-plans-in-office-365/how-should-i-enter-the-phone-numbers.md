---
title: 電話番号を入力する方法を教えてください。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 28aa24b4-8c81-4327-9752-989ea7540db2
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords: ms.lync.lac.PortOrderNumbers
ms.custom:
- Calling Plans
description: 'Skype for Business に発信するときに電話番号を設定する方法について説明します。 '
ms.openlocfilehash: df9d82a6e785954a95a455f0e43aa0e077f40bcf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280532"
---
# <a name="how-should-i-enter-the-phone-numbers"></a>電話番号を入力する方法を教えてください。

電話番号を移行するときは、正しい形式で入力する必要があります。 
  
> [!NOTE]
> 各電話番号または電話番号の範囲は、各行に個別に入力する必要があります。 
  
- 1つの電話番号を入力する場合:
    
  - すべての特殊文字は無視されます (ダッシュ "-" を含む)。 次に例を示します。
    
  - 10桁の番号の場合: ** &amp; \*(425\*() (\*&amp;4&amp;\*()) (\*250649**は、 **+ 14255550649**に修正されます)。
    
  - 11桁の番号の場合: **1\*() (\*&amp;42&amp;\*()\*&amp;(55550649**は、 **+ 14255550649**に修正されます。
    
  - 10桁または11桁の場合、すべてのタグが無視されます。 たとえば、 ** \<div> 4255551234\</div>** は **+ 14255551234**になります。
    
  - "-"、スペース、およびかっこは無視されます。 次に例を示します。
    
  - 10桁の番号の場合: **(425) 555-6776**は、 **+ 14255556776**に修正されます。
    
  - 11桁の番号の場合: **1 (425) 555-6776**は **+ 14255556776**に修正されます。
    
  - すべての文字は特殊文字として扱われ、10桁または11桁の電話番号がある場合は無視されます。 次に例を示します。
    
  - 10桁の番号の場合: **14jaosia2reoij05jof55506ajfoj49isdjf**は **+ 14255550649**に修正されます。
    
  - 11桁の番号の場合: **1ade4jaoda2rfoij05ojof55506dsfoj49if**は **+ 14255550649**に修正されます。
    
  - 他の言語でも、特殊文字の任意の組み合わせが修正されます。 次に例を示します。 
    
  - 10桁の番号の場合:**中文4中文 2ajj5\*() (\*(5 ()...551345**は **+ 14555551345**に修正されます。
    
  - 11桁の番号の場合:**中文4中文 2 $ a5\*() (\*(5 ()...55 (.1345**は **+ 14555551345**に修正されます。
    
  - 10桁未満か11桁を超える数値が含まれている場合は、ユーザーが修正できるように強調表示されます。
    
  - \*\*5551245\* \*は強調表示され、修正する必要があります。
    
  - **1234567891011**は強調表示され、修正する必要があります。
    
  - 10桁未満の数値、または特殊文字を含む11桁を超える数値は、自動的に修正されることなく強調表示されます。
    
  - 特殊文字が入力されていない7桁の数字の場合: **123456abcdefg7**は強調表示され、修正する必要がありますが、文字は無視されません。
    
  - 入力された特殊文字を含む7桁の数字の場合: **12345! @ # $&amp;\*% ^ ()--@ # $&amp;\*% ^ () 7**が強調表示され、修正されます。 特殊文字は無視されません。
    
- 電話番号の範囲を入力する場合。
    
  - 2つの電話番号のみを使用できます。 小さい数値は、範囲内の最初の数値である必要があります。
    
  - すべての特殊文字 (ダッシュ "-" 以外) は、1つの数値と同じように扱われます。 たとえば、 **(425) 555 0&amp;\*(123-(1425) 5557899nm**は、 **+ 14255550123-+ 13202040659**に修正されます。
    
  - "-" は、2つの数値のみを区切るために使われます。 数値の範囲に複数の "-" を含めることはサポートされていません。 たとえば、 **(425) 555-0649-(425) 555-1115**は、 **(425) 5550649-(425) 5551115**として入力する必要があります。
    
  **詳細な手順については、「 [Office 365 に電話番号を転送する](/microsoftteams/transfer-phone-numbers-to-office-365)」を参照してください。**

  > [!NOTE]
  > さらに追加で電話番号が必要な場合は、「[一般法人向け Office 365 のサポートへのお問い合わせ - 管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)」をご覧ください。

  
## <a name="related-topics"></a>関連トピック
[電話番号の移行に関するよくある質問](/microsoftteams/transferring-phone-numbers-common-questions)

[通話プランで使用されるさまざまな種類の電話番号](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[[[Skype for Business 新しい電話番号の申請](/microsoftteams/manage-phone-numbers-for-your-organization)] に移動することによって、電話番号を取得するために利用できるすべてのフォームを一覧表示してダウンロードすることができます。](/microsoftteams/manage-phone-numbers-for-your-organization)

[緊急通話の利用条件](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype for Business Online: 緊急通話の免責事項ラベル](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 