---
title: '[アナウンス] アプリケーションの展開Skype for Business Server'
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
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 72c66249-c4ce-48ce-b1b9-90ebf77d7805
description: 展開プロセスと、アナウンス アプリケーションの手順をSkype for Business Server エンタープライズ VoIP。
ms.openlocfilehash: 18345e8265ffed46f2e39d4acc8e0fca115731b4381efc64b98ecb4aba9e49c9
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54305929"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>[アナウンス] アプリケーションの展開Skype for Business Server
 
展開プロセスと、アナウンス アプリケーションの手順をSkype for Business Server エンタープライズ VoIP。
  
アナウンス アプリケーションは エンタープライズ VoIP 機能で、割り当てられていない内線番号 (組織で有効ですが、ユーザーまたは電話には割り当てられていない内線番号) への呼び出しに対する処理を構成できます。 たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。
  
アナウンス アプリケーションは、展開時にフロント エンド サーバーまたは Standard Edition サーバーに応答グループ アプリケーションの機能としてエンタープライズ VoIP。 オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。
  
このセクションでは、アナウンス アプリケーションの展開に関連する手順の概要について説明します。 アナウンスを構成する前エンタープライズ VoIPを展開する必要があります。 アナウンス アプリケーションで必要なコンポーネントは、アプリケーションを展開するときにインストールされエンタープライズ VoIP。
  
**アナウンスの展開プロセス**

|**フェーズ**|**手順**|**役割**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|アナウンス設定の構成  <br/> | 音声ファイルを録音およびアップロードするか、音声合成 (TTS) を使用してアナウンスを作成します。 <br/>  割り当てられていない番号テーブルで割り当てられていない番号範囲を構成し、適切なアナウンスに関連付ける。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[ユーザー設定でアナウンスを作成またはSkype for Business Server](create-an-announcement.md) <br/> [割り当てられていない番号範囲を作成または変更Skype for Business Server](create-or-modify-an-unassigned-number-range.md) <br/> |
|アナウンスの展開を確認する  <br/> |お知らせを聞いてテストし、構成が期待通り動作します。  <br/> |-  <br/> |[(省略可能)[アナウンスの展開を確認する] Skype for Business](optional-verify-announcement-deployment.md) <br/> |
   

