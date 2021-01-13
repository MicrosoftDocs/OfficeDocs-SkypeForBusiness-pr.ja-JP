---
title: Skype for Business でアナウンス アプリケーションを計画する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの計画。組織の割り当てられていない電話番号への通話に対する操作を構成します。 オーディオ ファイルの要件が含まれます。
ms.openlocfilehash: b1929fa14b105fd8eccd0f178ae7ef77c1bdf086
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813757"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Skype for Business でアナウンス アプリケーションを計画する

Skype for Business Server エンタープライズ VoIP でのアナウンス アプリケーションの計画。組織の割り当てられていない電話番号への通話に対する操作を構成します。 オーディオ ファイルの要件が含まれます。

Skype for Business Server アナウンス アプリケーションを使用すると、組織で有効なダイヤル番号がユーザーまたは電話に割り当てられていない場合に、着信呼び出しの処理を構成できます。 これらの通話を事前に設定しておいた転送先 (電話番号、SIP URI、またはボイス メール) に転送するか、音声アナウンスを再生するか、またはその両方を行うことができます。 アナウンス アプリケーションを使用することで、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。 このセクションには、アナウンス アプリケーションに固有の計画情報が含まれます。

アナウンス アプリケーションを展開する場合は、割り当てられていない番号をダイヤルした場合に実行されるアクションを決定する、割り当てられていない番号の表を構成する必要があります。 割り当てられていない番号の表には、組織で有効な電話番号の範囲と、各範囲を処理するアナウンス アプリケーションを指定します。 発信者が組織に対して有効な電話番号をダイヤルし、誰にも割り当てられていない場合、Skype for Business Server は割り当てられていない番号ルーティング テーブル内の番号を検索し、番号が入っている範囲を識別し、その範囲に指定されたアナウンス アプリケーションに通話をルーティングします。 アナウンス アプリケーションは通話に応答し、音声メッセージ (構成済みの場合) を再生してから、通話を切断するか、オペレーターに転送するなどの事前に定義された宛先に転送します。 Skype for Business Server 管理シェル コマンドレットを使用して、複数のオーディオ メッセージを構成したり、転送先を転送することができます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。 使用されなくなった特定の番号が存在し、各番号に合わせて調整されたメッセージを再生する場合は、割り当てられていない番号の表にそれらの特定の番号を入力できます。 たとえば、カスタマー サービス デスクの番号を変更した場合は、古い顧客サービス番号を入力し、新しい番号を提供するアナウンスに関連付けできます。 組織を離した従業員など、割り当てられていない番号に電話をかけ取るユーザーに対して一般的なメッセージを再生する場合は、組織内のすべての有効な内線番号の範囲を入力できます。 現在割り当てられていない番号を発信者がダイヤルするたびに、割り当てられていない番号テーブルが呼び出されます。

## <a name="deployment-and-requirements"></a>展開と要件

Tthe Announcement アプリケーションは、応答グループ アプリケーションと一緒に自動的にインストールされます。 アナウンス および応答グループ アプリケーションは、エンタープライズ VoIP 展開の標準コンポーネントです。エンタープライズ VoIP を展開すると、これらの両方のアプリケーションが自動的に展開されます。

### <a name="software-requirements"></a>ソフトウェア要件

アナウンス アプリケーションを実行するフロントエンド サーバーまたは Standard Edition サーバーはすべて、Windows Server 2008 R2 を実行するサーバー用に Windows Media フォーマット ランタイムをインストールするか、Windows Server 2012 または Windows Server 2012 R2 を実行するサーバー用の Microsoft Media Foundation をインストールする必要があります。 たとえばWindows Server 2008 R2、Windows Media フォーマット ランタイムは Windows デスクトップ エクスペリエンスの一部としてインストールされます。 お知らせや音楽のためにアナウンス アプリケーションが再生する Windows Media オーディオ (.wma) ファイルには、Windows Media フォーマット ランタイムまたは Microsoft Media Foundation が必要です。

### <a name="port-requirements"></a>ポートの要件

アナウンス アプリケーションは、SIP リッスン **要求にポート 5071** を使用します。

> [!NOTE]
> このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、Skype for Business Server 管理シェルのドキュメントを参照してください。

### <a name="audio-file-requirements"></a>オーディオ ファイルの要件

アナウンス アプリケーションは、音楽やアナウンスに Wave (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。 アナウンス アプリケーションのオーディオ ファイルの要件は、応答グループ アプリケーションの場合と同じです。 詳細については、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。


