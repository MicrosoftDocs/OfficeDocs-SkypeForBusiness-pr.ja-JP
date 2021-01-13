---
title: Skype for Business Server での統合連絡先ストアの計画
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '概要: Skype for Business Server と Exchange 2013 の統合を計画する場合は、このトピックを確認してください。'
ms.openlocfilehash: 3ce06118f8225e78c5c84a8f9124e4815f79d593
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816257"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 での統合連絡先ストアの計画
 
**概要:** Skype for Business Server と Exchange 2013 または 2016 の統合を計画する場合は、このトピックを確認してください。
  
統合連絡先ストアは、Microsoft Office 製品間で一貫した連絡先エクスペリエンスを提供し、ユーザーは Exchange 2013 のすべての連絡先情報を保存できますが、Skype for Business、Exchange、Outlook、および Outlook Web Access 全体でグローバルに情報を使用できます。
  
## <a name="requirements-for-unified-contact-store"></a>統合連絡先ストアの要件

Skype for Business Server に統合連絡先ストアを実装するには:
  
- Skype for Business Server と Exchange 2013 または 2016 を実行している必要があります。
    
- ユーザーは、Skype for Business Server から Exchange 2013 または 2016 に連絡先を移行するために Skype for Business を使用する必要があります。
    
- ユーザー メールボックスは Exchange 2013 に移行する必要があります。
    
- Skype for Business Server と Exchange 2013 または 2016 の間にサーバー間認証を構成する必要があります。
    
    > [!NOTE]
    > Skype for Business Server と Exchange 2013 または 2016 の間の認証のセットアップに関する詳細な要件については、「操作」のドキュメントの「Skype for Business Server でのサーバー間認証 [(OAuth)](../../manage/authentication/server-to-server-and-partner-applications.md) およびパートナー アプリケーションの管理」を参照してください。
  
## <a name="see-also"></a>関連項目

[Skype for Business Server での統合連絡先ストアの展開](../../deploy/deploy-unified-contact-store.md)
