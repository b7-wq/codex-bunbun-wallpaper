# Windows Codex �����޸���¼

���� CSS ���� 2026-10-13 �� Windows Store/MSIX Codex ʵ�⡣HeiGe ���� CSS ��λ�ü� Codex ������������汾�仯�����õ�ǰҳ�� DOM��������ʽ�ͽ�ͼ��λ���ٰ���Ҫ�Ĺ���������� CSS���޸ĺ�����Ӧ�����⡣

## ����ͼ

����ͼ������ͼƬ���������� `#root`����� Chromium �ᶪ������ data URL + `color-mix()` ���䡱��ϳɵ����� `background` ����������ͼƬ��ʹ�õ����� `background: url(...) right center / cover no-repeat`��͸���Ķ�����ھ���ؼ��ϣ����ѽ�ͬһ������������

## ������ť�������

��ȷ����Щ�����Զ�Ӧ���ڶ�����ҳ����⡣ǳ�ϵ׺�ģ�������Ͻǰ�ť����ǰ����������ǿշֿ���

```css
[class*="_ApplicationMenuTopBar_"] {
  background: linear-gradient(90deg,
    color-mix(in srgb, var(--heige-surface) 72%, transparent),
    color-mix(in srgb, var(--heige-surface) 97%, transparent)) !important;
  backdrop-filter: blur(14px) !important;
  color: var(--heige-text) !important;
  border-bottom: 1px solid color-mix(in srgb, var(--heige-accent) 24%, transparent) !important;
}

header[class*="_ApplicationMenuPageHeader_"] {
  background: color-mix(in srgb, var(--heige-surface) 86%, transparent) !important;
  backdrop-filter: blur(10px) !important;
  color: var(--heige-text) !important;
  border-top: 1px solid color-mix(in srgb, var(--heige-accent) 30%, transparent) !important;
  border-bottom: 1px solid color-mix(in srgb, var(--heige-accent) 36%, transparent) !important;
}
```

## ���������ĵײ�����

�ײ���������ռ�����ڣ�����խ������������������Ӳ�׿顣��׼ composer ����������Ԫ�غ󣬽������Ƶ��������ݿ��Ȳ��ữ���ࡣ

```css
[class*="thread-composer-bottom-inset"] > [class*="-top-8"][class*="z-0"] {
  left: 50% !important;
  right: auto !important;
  width: min(100%, var(--thread-content-max-width, 48rem)) !important;
  transform: translateX(-50%) !important;
  background: linear-gradient(180deg,
    transparent 0%,
    color-mix(in srgb, var(--heige-surface) 42%, transparent) 42%,
    color-mix(in srgb, var(--heige-surface) 68%, transparent) 100%) !important;
  backdrop-filter: blur(7px) !important;
  -webkit-mask-image: linear-gradient(90deg, transparent, #000 7%, #000 93%, transparent);
  mask-image: linear-gradient(90deg, transparent, #000 7%, #000 93%, transparent);
}
```

## �༭�ѷ�����Ϣ

��ͨ��Ϣ������ǳɫ�ף����༭״̬������һ������͸���� `form`����ɫ��ѹ���ǿ��ϡ�ֻ����Ϣ�༭�������Ķ��㣬������ס���ζԻ���

```css
[class*="group/user-message"] form:has([role="textbox"][contenteditable="true"]) {
  color: var(--heige-text) !important;
  background: color-mix(in srgb, var(--heige-surface) 92%, transparent) !important;
  border: 1px solid color-mix(in srgb, var(--heige-accent) 32%, transparent) !important;
  box-shadow: 0 8px 24px color-mix(in srgb, var(--heige-text) 14%, transparent) !important;
  backdrop-filter: blur(10px) !important;
}

[class*="group/user-message"] form [role="textbox"][contenteditable="true"] {
  color: var(--heige-text) !important;
  caret-color: var(--heige-accent) !important;
}
```

���Ӧ�ú�ļ�����ʽΪ 92% ǳ�ϱ�����`blur(10px)`������ `rgb(48, 35, 62)`������һ�� Codex �汾�У�����ʵ�ʴ򿪱༭��Ŀ�����ա�

