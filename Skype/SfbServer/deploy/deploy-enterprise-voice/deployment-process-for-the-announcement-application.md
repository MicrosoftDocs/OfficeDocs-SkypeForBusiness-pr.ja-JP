---
title: Skype for Business Server でのアナウンス アプリケーションの展開プロセス
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
description: Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの展開プロセスとエンタープライズ VoIP。
ms.openlocfilehash: cfb1436f22681b45de5c399907d4776a9d1db5de
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812307"
---
# <a name="deployment-process-for-the-announcement-application-in-skype-for-business-server"></a>Skype for Business Server でのアナウンス アプリケーションの展開プロセス
 
Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの展開プロセスとエンタープライズ VoIP。
  
アナウンス アプリケーションは エンタープライズ VoIP 機能で、割り当てられていない内線番号への呼び出しに対する処理を構成できます (組織で有効で、ユーザーや電話には割り当てられていない内線番号)。 たとえば、割り当てられていない番号に通話があった場合にメッセージを再生したり、別の通話先に転送したり、その両方を行ったりするように構成できます。
  
アナウンス アプリケーションは、展開時にフロント エンド サーバーまたは Standard Edition サーバーに応答グループ アプリケーションの機能としてエンタープライズ VoIP。 オーディオ ファイルをアップロードするか音声合成 (TTS) を構成して、割り当てられていない番号の表を構成し、アナウンスを構成する必要があります。
  
このセクションでは、アナウンス アプリケーションの展開に関連する手順の概要について説明します。 アナウンスを構成する前エンタープライズ VoIPを展開する必要があります。 アナウンス アプリケーションで必要なコンポーネントは、展開時にインストールされエンタープライズ VoIP。
  
**アナウンス展開プロセス**

|**フェーズ**|**手順**|**Roles**|**展開のドキュメント**|
|:-----|:-----|:-----|:-----|
|アナウンス設定を構成する  <br/> | オーディオ ファイルを録音してアップロードするか、音声合成 (TTS) を使用してアナウンスを作成します。 <br/>  割り当てられていない番号の表の割り当てられていない番号の範囲を構成し、それらを適切なアナウンスに関連付ける。 <br/> |RTCUniversalServerAdmins  <br/> CsVoiceAdministrator  <br/> CsServerAdministrator  <br/> CsAdministrator  <br/> CsViewOnlyAdministrator  <br/> |[Skype for Business Server でアナウンスを作成または削除する](create-an-announcement.md) <br/> [Skype for Business Server で割り当てられていない番号範囲を作成または変更する](create-or-modify-an-unassigned-number-range.md) <br/> |
|アナウンスの展開を確認する  <br/> |アナウンスを聞いてテストし、構成が期待通り動作を確認します。  <br/> |-  <br/> |[(省略可能)Skype for Business でのアナウンスの展開の確認](optional-verify-announcement-deployment.md) <br/> |
   

