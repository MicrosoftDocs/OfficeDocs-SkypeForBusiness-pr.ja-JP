---
title: SkypeRoom System の信頼されたドメイン
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Room System および Skypeの信頼できるドメインを構成するSkype for Business。
ms.openlocfilehash: 488b86e33035b39a1e189be7cc9191911250152e
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60830741"
---
# <a name="skype-room-system-trusted-domains"></a>SkypeRoom System の信頼されたドメイン
 
このトピックでは、Room System および Skypeの信頼できるドメインを構成するSkype for Business。
  
## <a name="trusted-domains"></a>信頼済みドメイン

Skype for Business クライアントにはダイアログ ボックスが表示され、ユーザー アカウントサインインの SIP ドメインが証明書のサブジェクトまたはサブジェクトの Alt 名に示されている名前と異なる場合、ユーザーは Skype for Business Server からの証明書を受け入れできます。 組織内の Skype for Business Server 用に構成された証明書に、Subject または Subject Alt Name の Skype Room System アカウントの SIP ドメイン名が含されていない場合は、Skype Room System コンソール マシンの信頼されたドメイン レジストリ キーの下にある証明書に表示されるドメインを構成する必要があります。 Room System Skype提供の Skype管理者ガイドでは、クライアントに信頼できるドメインを追加する方法と場所Skype for Business説明します。 
  
たとえば、証明書で構成された証明書に"CONTOSO Skype for Business Serverサブジェクト/サブジェクトの Alt 名を指定するとします。LOCAL」 と、Room System サインイン アドレスのユーザーに割り当Skype SIP ドメインの 1 つが "confrm1@contoso.net。 contoso.net は証明書に含めないので、Skype Room System コンピューターでは、Skype Room System 製造元が提供する Skype Room System Administrator's Guide で説明したように、レジストリ内の信頼できるドメインとして "contoso.local" を構成する必要があります。 
  

