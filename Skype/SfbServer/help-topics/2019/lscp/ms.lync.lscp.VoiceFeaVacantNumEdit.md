---
title: 割り当てられていない電話番号を新規作成または既存の編集
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceFeaVacantNumEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 58903e40-6b93-40d6-88f8-1201743cd9be
ROBOTS: NOINDEX, NOFOLLOW
description: 未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。
ms.openlocfilehash: 176e1b0485b9fc9584b770e4708cad0bf0662e00
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897365"
---
# <a name="unassigned-phone-number-create-new-or-edit-existing"></a>割り当てられていない電話番号: 新規作成または現在の形式のままで編集

> [!NOTE]
> Exchange UM のまま Skype で利用可能なビジネス サーバー 2019 の Exchange 2013 または Exchange 2016 2019 のビジネス用の Skype を統合する場合です。 2019 の Exchange でのサポートの変更により、Exchange UM の統合は、ボイスメールのクラウドとクラウドの自動応答の機能のための emphasised ことです。

未使用の番号とは、組織にとって有効であるが、ユーザーや電話に割り当てられていない電話番号です。未使用の番号の表は、それらの番号に対して発信があった場合の対処方法を示します。

> [!IMPORTANT]
> 新しい割り当てられていない番号範囲を作成または既存の編集が終了したら、すべての数値の範囲を示す**番号が割り当てられていない**ページに戻るには **[ok]** をクリックします。 **新しい未割り当ての番号範囲**] ページまたは **[割り当てられていない番号 Rage の編集**ページに加えた変更は、[**割り当てられていない番号**] ページ**のすべてのコミット**をクリックするまでにはデータベースにコミットされません。

## <a name="ui-reference"></a>UI リファレンス

次の一覧に、このページのフィールドを示します。

- **名**未使用の番号の範囲を識別するわかりやすい名前を入力します。 範囲を保存すると、この名前は変更できません。

- **番号の範囲**最初のフィールドに割り当てられていない番号の範囲の開始番号を入力します。 2 番目のフィールドには、範囲の終了番号を入力します。

  - 範囲の開始番号が終了番号より大きくならないようにしてください。

  - 範囲の開始番号または終了番号に内線番号が含まれる場合は、両方の番号が内線番号を含む必要があり、その内線番号は両方の番号で一致する必要があります。

  - 番号が正規表現に一致する必要があります (tel:) ? (\+) ? [1-9] \d{0,17}(; ext = [1-9] \d{0,9}) ?。 つまり、番号の先頭に文字列 tel: (その文字列を指定しない場合に自動的に追加)、プラス記号 (+) と数字の 1 9 から。 電話番号が最大 17 桁にすることができ、拡張した形式で続いて ext = 内線番号の後にします。

- **サービスのお知らせ****発表**のお知らせアプリケーションが着信呼び出しを処理するか、 **Exchange UM**を Exchange UM 自動応答着信呼び出しを処理するを選択します。

- **お知らせサービス**の**お知らせ**を選択した場合。

  - **宛先サーバーの FQDN**この範囲の割り当てられていない番号への着信呼び出しを処理するアナウンス アプリケーションを実行するアプリケーション サービスのサービス ID を選択します。

  - **お知らせ**この割り当てられていない番号の範囲を再生するアナウンスを選択します。

- **Exchange UM** **サービスのお知らせ**を選択した場合。

  - **自動応答の電話番号**Exchange UM 自動応答の電話番号を選択します。

発表の特徴と機能についての詳細は、計画ドキュメントに[ビジネス用の Skype で知らせアプリケーションの計画](../../../plan-your-deployment/enterprise-voice-solution/announcement.md)を参照してください。 未使用の番号範囲の使用の詳細については、「操作」のドキュメントの「[Configure Routing of Unassigned Phone Numbers](https://technet.microsoft.com/library/a0650659-dce7-455f-8977-02454bbfa400.aspx)」を参照してください。


