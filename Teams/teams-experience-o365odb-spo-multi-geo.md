---
title: Office 365 One および SharePoint Online Multi-Geo 対応テナントでの Teams のエクスペリエンス
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: snigdhav
description: Office 365 OneDrive と SharePoint Online の複数の Geo 対応のテナントで Teams を使用する方法について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e90e4a3c1ae2886a01802a805da3464cea3d8b50
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32204500"
---
<a name="teams-experience-in-an-office-365-onedrive-and-sharepoint-online-multi-geo-enabled-tenancy"></a>Office 365 One および SharePoint Online Multi-Geo 対応テナントでの Teams のエクスペリエンス
===========================================

Microsoft Teams は、グループチャットソフトウェアであり、Office 365 でのチームワークのハブです。 この機能は、Office 365 Groups サービスと SharePoint Online および OneDrive for Business のファイルエクスペリエンスによって実現されています。 OneDrive for Business/SharePoint Online の複数地域のテナント (北米、ヨーロッパ、オーストラリアなど、さまざまな地理的な場所にテナントが拡張されている場合、基盤となるファイルのエクスペリエンスは複数の地域に対応しているため、Teams でファイルを操作することができるためです)。コラボレーションも複数の地域に対応しています。 これは、ネイティブファイルエクスペリエンスで複数の Geos でホストされているファイルを処理するための主要な最先端機能です。

たとえば、欧州を使用する Contoso のテナントが、中央の Geo としてサテライトの Geo と北米として表示されている場合、ファイルはヨーロッパのデータの場所と米国でホストされていますが、ヨーロッパの衛星ユーザーは左側のウィンドウの [ファイル] タブに自分の OneDrive ファイルを表示します。es はテナントの中央の場所です。 また、最新のビューブレードで、最近使用したファイルにアクセスすることもできます。 最近使用したファイルには、他の Geos のユーザーから共有されているファイルが含まれている可能性があります。また、テナントが拡張されている他の Geo の場所でもそのようになっている場合 

特定のチームのグループサイトも、複数の地域に対応しています。 つまり、ヨーロッパのサテライトユーザーがチームを作成している場合、対応するグループサイトはヨーロッパの場所に作成され、そのチームグループに関連付けられたファイルは、その場所の残りの部分に保存されます。 新しいファイルをアップロードしたり、ファイルを編集したりするなど、以降のすべてのエクスペリエンスは、そのヨーロッパの場所を対象としているため、これらのファイルに対してデータを確実に保持できます。 これは、基盤となる foundation Office 365 グループによって、複数の地域に対応できるようになりました。

複数の Geo のテナントは1つのグローバルテナントであるため、@ メンションを実行しているユーザーは、どこにいても、世界中の同僚を見ることができます。 

チームエクスペリエンス内でのチャットおよび会議 IM のメモの会話は、複数の地域に認識されず、すべてがテナントの中央の場所でのみ保持されることに注意してください。 通常、チャットの会話はデータ常駐のニーズには適用されません。

複数の地域での Office 365 の詳細については、「 [Microsoft の多機能機能」ページ](https://aka.ms/multi-geo)を参照してください。