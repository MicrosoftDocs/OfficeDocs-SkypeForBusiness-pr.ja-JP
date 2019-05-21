---
title: Skype for Business Server の統合連絡先ストアの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 6/8/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d56e11be-43dd-45d4-8ac6-3adfb03f5d1a
description: '概要: Skype for Business Server と Exchange 2013 との統合を計画しているときに、このトピックを確認してください。'
ms.openlocfilehash: 4548773c382b4295ddfbfa141f18f0df8ba367ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297394"
---
# <a name="plan-for-unified-contact-store-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 の統合連絡先ストアの計画
 
**概要:** Skype for Business Server を Exchange 2013 または2016に統合する計画中に、このトピックを確認してください。
  
統合連絡先ストアでは、Microsoft Office 製品全体で一貫した連絡先エクスペリエンスを提供し、ユーザーは Exchange 2013 ですべての連絡先情報を保存できますが、情報は Skype for Business、Exchange、Outlook でグローバルに利用できます。、Outlook Web Access などがあります。
  
## <a name="requirements-for-unified-contact-store"></a>統合連絡先ストアの要件

Skype for Business Server でユニファイド連絡先ストアを実装するには、次の操作を行います。
  
- Skype for Business Server および Exchange 2013 または2016を実行している必要があります。
    
- ユーザーは skype for Business を使用して、Skype for Business Server から Exchange 2013 または2016に連絡先を移行する必要があります。
    
- ユーザーのメールボックスは Exchange 2013 に移行する必要があります。
    
- Skype for Business Server と Exchange 2013 または2016の間にサーバー間認証が構成されている必要があります。
    
    > [!NOTE]
    > Skype for Business Server と Exchange 2013 または2016の間の認証のセットアップの詳細については、「 [skype For Business server でのサーバー間認証 (OAuth) とパートナーアプリケーションの管理](../../manage/authentication/server-to-server-and-partner-applications.md)」を参照してください。documentation.
  
## <a name="see-also"></a>関連項目

[Skype for Business Server にユニファイド連絡先ストアを展開する](../../deploy/deploy-unified-contact-store.md)
