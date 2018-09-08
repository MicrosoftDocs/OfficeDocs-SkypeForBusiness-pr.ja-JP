---
title: Skype for Business Server と Skype for Business Online 間でハイブリッド接続を展開する
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 12/8/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
description: '概要: このトピックでは、Skype for Business Server と Skype for Business Online 間でハイブリッド接続を展開する方法を説明します。'
ms.openlocfilehash: 1e42b0c582f186b785db691e66b9ee88aa6d6a74
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886197"
---
# <a name="deploy-hybrid-connectivity-between-skype-for-business-server-and-skype-for-business-online"></a>Skype for Business Server と Skype for Business Online 間でハイブリッド接続を展開する
 
**概要:** このトピックでは、Skype for Business Server と Skype for Business Online 間でハイブリッド接続を展開する方法を説明します。
  
このトピックの手順を実行する前にする必要があります読んだ[ビジネス サーバーとオンライン ビジネスの Skype の Skype 間でのハイブリッド接続を計画](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)します。
  
Skype ビジネス サーバーとビジネス オンラインの Skype との間のハイブリッドの接続では、contoso.com などのドメインのユーザーが社内のビジネス サーバーと Skype の Skype を使用してオンライン ビジネスの間で分割を意味します。 一部のドメイン ユーザーはオンプレミスに所属し、その他のユーザーはオンラインに所属します。 
  
次の表は、ビジネスをオンラインで、Microsoft Office 365 の Skype でハイブリッド展開の環境を準備するために必要な手順を示します。 
  
|**ステップ**|**説明**|
|:-----|:-----|
|Office 365 テナント アカウントを作成し、オンライン ビジネスの Skype を有効にします。  <br/> |[Office 365](https://go.microsoft.com/fwlink/p/?LinkId=254980)のオンライン ビジネスでは、Office 365 と Skype について説明します。  <br/> お客様の環境が Office 365 の準備ができていることを確認するには、[システム要件](https://products.office.com/en-US/office-system-requirements)を参照してください。  <br/> Office 365 のセットアップの詳細については、 [Office 365 の概要](https://go.microsoft.com/fwlink/p/?LinkId=254982)を参照してください。  <br/> |
|Office 365 テナントに自分のドメインを追加し、所有権を確認  <br/> | Office 365 テナントにドメインを追加して、Office 365 でそのドメインを検証します。 この検証は、ドメインの所有者が自分であることを確認するために必要な手順です。 <br/> Office 365 テナントに自分のドメインを追加するには、以下の[Office 365 にドメインを追加](https://support.office.com/en-us/article/add-a-domain-to-office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611?ui=en-US&rs=en-US&ad=US)で説明した手順を。  <br/> |
|作業中のディレクトリ同期を準備します。  <br/> |作業中のディレクトリ同期処理では、Office 365 と同期して継続的に、オンプレミスの Active Directory を保持します。 これにより、各ユーザー アカウントおよびグループの同期バージョンを作成できるだけでなく、ローカルの Microsoft Exchange Server 環境から Microsoft Exchange Online へのグローバル アドレス一覧 (GAL) の同期を実行できるようになります。 詳細については、[ディレクトリの統合ツール](https://go.microsoft.com/fwlink/p/?LinkId=530320)を参照してください。  <br/>  **重要**オンライン ビジネスのユーザーが Skype に移動しない場合でも、設置とオンラインの展開では、組織内のビジネス ユーザー向けのすべての Skype の AD のアカウントを同期する必要があります。 すべてのユーザーを同期しない場合、組織のオンプレミス展開のユーザーとオンライン ユーザーとの間の通信が正常に動作しない可能性があります。           |
|パイロット ユーザーを移動する  <br/> |準備し、Skype のオンライン ビジネスの環境を構成する手順を完了したら、パイロット ユーザーをオンラインの Office 365 テナントに移行を開始できます。 [Skype ビジネスをオンラインにするには、社内設置型からユーザーを移動する](move-users-from-on-premises-to-skype-for-business-online.md)を参照してください。  <br/> |
