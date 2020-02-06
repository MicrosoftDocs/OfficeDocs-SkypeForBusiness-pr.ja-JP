---
title: Skype for Business でのお知らせアプリケーションの計画
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Skype for Business Server エンタープライズ Voip のお知らせアプリケーションの計画。組織内の未割り当ての電話番号への通話で何を行うのかを設定します。 また、オーディオ ファイルの要件についても説明します。
ms.openlocfilehash: d160878030fad30dd3e91b78f54ffcdab722299f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803267"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>Skype for Business でのお知らせアプリケーションの計画

Skype for Business Server エンタープライズ Voip のお知らせアプリケーションの計画。組織内の未割り当ての電話番号への通話で何を行うのかを設定します。 また、オーディオ ファイルの要件についても説明します。

Skype for Business Server アナウンスメントアプリケーションを使用すると、ダイヤルされた番号が組織で有効であるが、ユーザーまたは電話に割り当てられていない場合に、着信通話の処理を構成することができます。 これらの通話を事前に設定しておいた転送先 (電話番号、SIP URI、またはボイス メール) に転送するか、音声アナウンスを再生するか、またはその両方を行うことができます。 アナウンス アプリケーションを使用することで、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。 このセクションには、アナウンスメントアプリケーションに固有の計画情報が記載されています。

アナウンスメントアプリケーションを展開するときに、割り当てられていない番号をダイヤルしたときに実行されるアクションを決定する、割り当てられていない番号テーブルを構成する必要があります。 割り当てられていない番号テーブルには、組織で有効な電話番号の範囲が含まれており、各範囲を処理するアナウンスメントアプリケーションが指定されています。 発信者が組織で有効な電話番号をダイヤルしたが、すべてのユーザーに割り当てられていない場合、Skype for Business Server は、割り当てられていない番号ルーティングテーブルの番号を検索し、その番号がどの範囲にあるかを特定して、通話をその範囲に対して指定されたアナウンスメントアプリケーション。 アナウンスメントアプリケーションは、通話に応答し、音声メッセージを再生し (設定している場合)、電話を切断するか、オペレーターなどの事前に定義された宛先に転送します。 Skype for Business Server Management Shell コマンドレットを使用して、複数の音声メッセージを構成したり、送信先を転送したりできます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。現在使用されていない特定の番号があり、各番号用に作成したメッセージを再生する必要がある場合、これらの特定の番号を割り当てられていない番号の表に入力できます。たとえば、顧客サービス デスクの番号を変更した場合、古い顧客サービス番号を入力して、新しい番号を知らせるアナウンスをその番号に関連付けることができます。組織から離れた従業員の番号など、割り当てられていない番号を呼び出す発信者に対して一般的なメッセージを再生する必要がある場合、組織内のすべての有効な内線番号の範囲を入力できます。割り当てられていない番号の表は、発信者が現在割り当てられていない番号をダイヤルすると常に呼び出されます。

## <a name="deployment-and-requirements"></a>展開と要件

このアナウンスメントアプリケーションは、応答グループアプリケーションと共に自動的にインストールされます。 お知らせと応答グループのアプリケーションは、エンタープライズ Voip 展開の標準的なコンポーネントです。エンタープライズボイスを展開すると、これらの両方のアプリケーションが自動的に展開されます。

### <a name="software-requirements"></a>ソフトウェア要件

アナウンスメントアプリケーションを実行するすべてのフロントエンドサーバーまたは標準エディションのサーバーは、windows server 2008 R2 を実行しているサーバー、または Windows Server 2012 を実行しているサーバーの Microsoft メディアファンデーションに Windows Media Format ランタイムをインストールする必要があります。Windows Server 2012 R2。 Windows Server 2008 R2 の場合、windows Media 形式ランタイムは Windows デスクトップエクスペリエンスの一部としてインストールされます。 Windows media Format Runtime または Microsoft メディアファンデーションは、アナウンスメントアプリケーションがお知らせや音楽を再生するために Windows Media オーディオ (.wma) ファイルを使用する場合に必要です。

### <a name="port-requirements"></a>ポートの要件

アナウンスメントアプリケーションは、SIP リスニング要求に**ポート 5071**を使用します。

> [!NOTE]
> このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「Skype for Business Server 管理シェルのドキュメント」を参照してください。

### <a name="audio-file-requirements"></a>オーディオ ファイルの要件

アナウンスメントアプリケーションは、音楽とお知らせのウェーブ (.wav) ファイル形式と Windows Media オーディオ (.wma) ファイル形式をサポートしています。 アナウンスメントアプリケーションのオーディオファイルの要件は、応答グループアプリケーションの場合と同じです。 詳細は、「[Technical Requirements for Response Groups](https://technet.microsoft.com/library/477488bd-124f-437b-9327-732a0d7271ca.aspx)」を参照してください。


