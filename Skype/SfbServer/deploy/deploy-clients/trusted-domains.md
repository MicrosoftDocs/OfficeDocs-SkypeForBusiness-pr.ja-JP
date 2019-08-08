---
title: Skype Room System の信頼されたドメイン
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: 2b2aeb98e3b1b6efe585e565c1e288d635fdb26e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235016"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Room System の信頼されたドメイン
 
このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
  
## <a name="trusted-domains"></a>信頼されたドメイン

Skype for Business クライアントに表示されるダイアログボックスを使用すると、ユーザーアカウントの SIP ドメインが証明書のサブジェクト名またはサブジェクト名に表示される名前とは異なる場合に、ユーザーが Skype for Business Server の証明書を受け入れることができます。 組織内の Skype for Business Server 用に構成された証明書に、Skype Room System アカウントの SIP ドメイン名がサブジェクトまたはサブジェクトの代替名に含まれていない場合は、信頼済みドメインの証明書に記載されているドメインを構成する必要があります。Skype Room System コンソールコンピューターのレジストリキー。 Skype Room システムの製造元によって提供される Skype Room システム管理者ガイドで、Skype for Business クライアントで信頼済みドメインを追加する方法と場所について説明します。 
  
たとえば、Skype for Business Server で構成されている証明書のサブジェクト/件名の代替名が "CONTOSO" であるとします。ローカル「Skype Room System サインインアドレス用にユーザーに割り当てられている SIP ドメインの1つは "confrm1@contoso.net" です。 Contoso.net は証明書に登録されていないため、Skype Room システムコンピューターでは、skype Room system のメーカーによって提供されている Skype room システム管理者ガイドで説明されているように、信頼できるドメインとして "コントソ .local" を設定する必要があります。 
  

