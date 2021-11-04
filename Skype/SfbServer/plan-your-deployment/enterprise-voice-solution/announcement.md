---
title: '[アナウンス] アプリケーションの計画をSkype for Business'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
description: 組織の割り当てられていない電話番号に対する電話の操作を構成する Skype for Business Server エンタープライズ VoIP でアナウンス アプリケーションを計画します。 オーディオ ファイルの要件が含まれています。
ms.openlocfilehash: 26dbd9a0bf1513812cb08034216194ca67a92b39
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/04/2021
ms.locfileid: "60778097"
---
# <a name="plan-for-the-announcement-application-in-skype-for-business"></a>[アナウンス] アプリケーションの計画をSkype for Business

組織の割り当てられていない電話番号に対する電話の操作を構成する Skype for Business Server エンタープライズ VoIP でアナウンス アプリケーションを計画します。 オーディオ ファイルの要件が含まれています。

[Skype for Business Serverアナウンス] アプリケーションを使用すると、ダイヤルされた番号が組織で有効ですが、ユーザーまたは電話に割り当てられていないときに、着信電話の処理を構成できます。 これらの通話を事前に設定しておいた転送先 (電話番号、SIP URI、またはボイス メール) に転送するか、音声アナウンスを再生するか、またはその両方を行うことができます。 アナウンス アプリケーションを使用することで、発信者が誤ってダイヤルしたり、話し中の音が流されたり、または SIP クライアントがエラー メッセージを受け取ったりするような状況を避けることができます。 このセクションには、アナウンス アプリケーションに固有の計画情報が含まれています。

アナウンス アプリケーションを展開する場合は、割り当てられていない番号をダイヤルするときに実行するアクションを決定する割り当てられていない番号テーブルを構成する必要があります。 割り当てられていない番号テーブルには、組織で有効な電話番号の範囲が含まれているので、各範囲を処理するアナウンス アプリケーションを指定します。 発信者が組織に対して有効だが、誰にも割り当てられていない電話番号にダイヤルすると、Skype for Business Server は割り当てられていない番号ルーティング テーブル内の番号を検索し、番号が入る範囲を識別し、その範囲に指定されたアナウンス アプリケーションに通話をルーティングします。 アナウンス アプリケーションは呼び出しに応答し、音声メッセージを再生します (これを構成した場合)、通話を切断するか、オペレーターなど、所定の宛先に転送します。 管理シェルコマンドレットSkype for Business Server使用して、複数のオーディオ メッセージを構成したり、宛先を転送することができます。

割り当てられていない番号の表の構成方法はその使用方法によって異なります。 使用されなくなった特定の番号が存在し、各番号に合わせて調整されたメッセージを再生する場合は、割り当てられていない番号テーブルにそれらの特定の番号を入力できます。 たとえば、顧客サービス デスクの番号を変更した場合は、古い顧客サービス番号を入力し、新しい番号を示すアナウンスに関連付けできます。 割り当てられていない番号を呼び出すユーザー (組織を離した従業員など) に対して一般的なメッセージを再生する場合は、組織内のすべての有効な内線番号の範囲を入力できます。 割り当てられていない番号テーブルは、発信者が現在割り当てられていない番号をダイヤルするたびに呼び出されます。

## <a name="deployment-and-requirements"></a>展開と要件

Tthe Announcement アプリケーションは、応答グループ アプリケーションと一緒に自動的にインストールされます。 アナウンス および応答グループ アプリケーションは、エンタープライズ VoIP 展開の標準コンポーネントです。エンタープライズ VoIP を展開すると、これらの両方のアプリケーションが自動的に展開されます。

### <a name="software-requirements"></a>ソフトウェア要件

アナウンス アプリケーションを実行するすべてのフロントエンド サーバーまたは Standard Edition サーバーには、Windows Server 2008 R2 を実行しているサーバー用に Windows メディア形式ランタイムがインストールされている必要があります。または Windows Server 2012 または Windows Server 2012 R2 を実行しているサーバーの場合は Microsoft Media Foundation がインストールされている必要があります。 Server 2008 R2 Windowsでは、Windows メディア形式ランタイムがデスクトップ エクスペリエンスの一部Windowsされます。 Windowsアナウンス アプリケーションがアナウンスや音楽のために再生するメディア オーディオ (.wma) ファイルWindowsメディア 形式ランタイムまたは Microsoft Media Foundation が必要です。

### <a name="port-requirements"></a>ポートの要件

アナウンス アプリケーションは **、SIP リッスン要求にポート 5071** を使用します。

> [!NOTE]
> このポートは既定の設定であり、**Set-CsApplicationServer** コマンドレットを使用して変更することができます。 このコマンドレットの詳細については、「管理シェル」Skype for Business Serverを参照してください。

### <a name="audio-file-requirements"></a>オーディオ ファイルの要件

アナウンス アプリケーションは、Wave (.wav) ファイル形式をサポートし、Windowsアナウンス用のメディア オーディオ (.wma) ファイル形式をサポートします。 アナウンス アプリケーションのオーディオ ファイル要件は、応答グループ アプリケーションと同じです。 詳細については、「[Technical Requirements for Response Groups](/previous-versions/office/lync-server-2013/lync-server-2013-technical-requirements-for-response-group)」を参照してください。