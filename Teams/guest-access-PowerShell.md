---
title: "PowerShell を使用してチームにゲスト アクセスを制御するには"
author: LaithAlShamri
ms.author: laal
manager: lolaj
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
description: "許可または Microsoft チームでチームにゲスト アクセスをブロックするには、PowerShell を使用します。"
ms.openlocfilehash: d75bbbce689b5b0799c7d2ec806977f6d23ee906
ms.sourcegitcommit: 2d84f687ccc44220d5ec9d8b429dfae65cced5a7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2018
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a>PowerShell を使用してチームにゲスト アクセスを制御するには
================================================

に加えて、Office 365 管理センターと Azure Active Directory ポータルを使用して、ゲスト アクセスを制御するのに Windows PowerShell を使用することができます。PowerShell] で、次の操作を行います。
  
  
   

- 許可またはすべてのチームと Office 365 グループへのゲスト アクセスをブロックします。
    
  
- すべてのチームと Office 365 のグループに追加するゲストを許可します。
    
  
- 許可または特定のチーム サイトまたは Office 365 グループからゲスト ユーザーをブロックします。
    
  
詳細については、[ [Office 365 のグループ内のゲスト アクセス許可](https://support.office.com/en-us/article/Use-PowerShell-to-control-guest-access-bfc7a840-868f-4fd6-a390-f347bf51aff6#bkmk_usepowershell)の管理] タブの「ゲスト アクセスを制御する PowerShell を使用する」セクションを参照してください。
  
    
    
許可または自分のドメインに基づくゲスト ユーザーをブロックする PowerShell を使用することもできます。たとえば、別のビジネス (Fabrikam) のパートナーシップをビジネス (Contoso) があるとします。許可リストに Fabrikam を追加するには、ユーザーのグループにこれらのゲストを追加できるようにします。詳細については、 [Office 365 のグループへのゲスト アクセスの許可/禁止](https://go.microsoft.com/fwlink/?linkid=854001)を参照してください。
  
 
チームのゲストをブロックし、ながら、ゲスト SharePoint サイトにアクセスする場合は、コマンドレットを使用できます Powershell Azure Active Directory、会社のオブジェクトに AllowGuestAccessToGroups パラメーターを無効にする外部共有を有効になっているものとしてSharePoint サイトです。   

