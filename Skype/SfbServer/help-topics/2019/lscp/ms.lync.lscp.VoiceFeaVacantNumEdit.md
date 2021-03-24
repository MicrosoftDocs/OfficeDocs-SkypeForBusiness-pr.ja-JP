---
title: 割り当てられていない電話番号 新規の作成または既存の編集
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 49837269f81eaee09a0c191008234345d1d6d19f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097053"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>割り当てられていない電話番号: 新規作成または現在の形式のままで編集

> [!NOTE]
> Skype for Business Server 2019 を Exchange 2013 または Exchange 2016 に統合すると、Exchange UM は Skype for Business Server 2019 で引き続き使用できます。 Exchange 2019 でのサポートの変更により、Exchange UM の統合はクラウド ボイスメール機能とクラウド ボイスメール機能の機能を重視自動応答されています。

未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。

> [!IMPORTANT]
> 新しい未使用の番号範囲の作成または既存の未使用の番号範囲の編集が終了して [**OK**] をクリックすると、[**未使用の番号**] ページに戻り、すべての番号範囲が表示されます。[**新規 未使用の番号範囲**] ページまたは [**編集 未使用の番号範囲**] ページで行った変更は、[**未使用の番号**] ページで [**すべてコミット**] をクリックするまでは、データベースにコミットされません。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前** 割り当てられていない番号範囲を識別するわかりやすい名前を入力します。 範囲を保存した後、この名前を変更することはできません。

- **数値範囲** 最初のフィールドに、割り当てられていない番号範囲の先頭番号を入力します。 2 番目のフィールドに、範囲の終了番号を入力します。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。

  - 数値は正規表現 ( `tel:` )?( )と一致 \+ する必要があります。[1-9]\d {0,17} (;ext=[1-9]\d {0,9} )?. つまり、番号は文字列 'tel:' で始まる可能性があります。 その文字列を指定しない場合は、プラス記号 (+)、数字 1 ~ 9 など、自動的に追加されます。 電話番号には最大 17 桁の数字を指定できます。その後に内線番号 ;ext= の後に内線番号を付けることもできます。

- **アナウンス サービス** アナウンス **アプリケーションが** 着信呼び出しまたは **Exchange UM** を処理するには、[アナウンス] を選択して、着信呼び出しを処理自動応答 Exchange UM を持つ必要があります。

- [**アナウンス サービス**] で [**アナウンス**] を選択した場合:

  - **宛先サーバーの FQDN** 割り当てられていないこの範囲の着信呼び出しを処理するアナウンス アプリケーションを実行する Application サービスのサービス ID を選択します。

  - **お知らせ** 割り当てられていないこの範囲の番号に対して再生するアナウンスを選択します。

- [**アナウンス サービス**] で [**Exchange UM**] を選択した場合:

  - **自動応答電話番号** Exchange UM サーバーの電話番号を自動応答。

アナウンスの機能の詳細については、「計画」のドキュメントの「Plan for the [Announcement application in Skype for Business」](../../../plan-your-deployment/enterprise-voice-solution/announcement.md) を参照してください。 未使用の番号範囲の操作の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](/previous-versions/office/lync-server-2013/lync-server-2013-configure-unassigned-phone-numbers)」を参照してください。