---
title: (省略可能)Skype for Business でのコール パーク展開の確認
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Skype for Business Server エンタープライズ VoIP でのコール パークの展開のエンタープライズ VoIP。
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830897"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>(省略可能)Skype for Business でのコール パーク展開の確認
 
Skype for Business Server サービスでのコール パークの展開エンタープライズ VoIP。 
  
コール パークをインストールして構成した後、構成を確認して、通話のパークと取得が期待通り動作する必要があります。 少なくとも、以下を確認してください。
  
- コール パークが有効になっているユーザーを呼び出し、そのユーザーに通話をパークします。
    
    > [!NOTE]
    > このテストを実行する直前に音声ポリシーでコール パークを有効にした場合、通話をパークしているユーザーは、転送通話リストにコール パーク オプションを表示するために、Skype for Business からサインアウトしてからサインインし戻す必要があります。 
  
- オービット番号をダイヤルして、電話を取ります。
    
- 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。
    

