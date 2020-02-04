---
title: 未割り当ての電話番号の新規作成または既存の編集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 51b66f7b3fffaf647970cb29b300b75460b0adce
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2020
ms.locfileid: "41703912"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>割り当てられていない電話番号: 新規作成または現在の形式のままで編集

> [!NOTE]
> Skype for business 2019 を Exchange 2013 または Exchange 2016 と統合すると、exchange UM は Skype for Business Server 2019 で利用可能になります。 Exchange 2019 のサポートが変更されたため、クラウドボイスメールとクラウド自動応答機能を利用して、Exchange UM との統合を強調することができます。

未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。

> [!IMPORTANT]
> 割り当てられていない新しい番号範囲の作成または既存の番号範囲の編集が完了したら、[ **OK]** をクリックして、すべての数値範囲を一覧表示する [**未使用の番号**] ページに戻ります。 [未使用の番号 **] ページで**行った変更、または [割り当てられていない番号の**編集** **] ページで**[**コミット**] をクリックするまで、データベースにコミットされません。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名前**割り当てられていない番号の範囲を示すわかりやすい名前を入力します。 範囲を保存した後は、この名前を変更することはできません。

- **数値の範囲**最初のフィールドに、割り当てられていない番号の範囲の開始番号を入力します。 2番目のフィールドに、範囲の終了番号を入力します。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。

  - 数値は正規表現 (tel:) に一致する必要があります。 (\+)?[1-9] \d{0,17}(; ext = [1-9] \d{0,9})? これは、数値が文字列 "tel" で始まる可能性があることを意味します (この文字列は自動的に追加されるように指定していない場合)。プラス記号 (+)、1 ~ 9 桁の数字です。 電話番号は最大17桁で、その後に形式の内線番号、内線番号、内線番号が続く場合があります。

- **アナウンスメントサービス**[**お知らせ**] を選択すると、アナウンスメントアプリケーションは着信通話または**exchange um**を処理して、着信呼び出しを処理します。

- **アナウンスメントサービス**で**お知らせ**を選択した場合:

  - **転送先サーバーの FQDN**この範囲の未割り当て番号への着信通話を処理するアナウンスメントアプリケーションを実行するアプリケーションサービスのサービス ID を選択します。

  - **お知らせ**この範囲の未割り当ての番号に対して再生するお知らせを選択します。

- **EXCHANGE UM**で**お知らせサービス**を選択した場合:

  - **自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。

お知らせ機能と機能の詳細については、計画ドキュメントの「 [Skype For business のアナウンスメントアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)」を参照してください。 未使用の番号範囲の使用の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。


