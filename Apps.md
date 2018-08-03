# App Developer Collections

1. 从粘贴板赋值过来的内容只允许输入数字类型

```objective-c
// 在UI层监听UITextField的代理
-(BOOL)textField:(UITextField *)textField shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string {
    if (string.length > 1) {
        NSString * afterCutString = @"";
        for(int i =0; i < [string length]; i++)
        {
            NSString * temp = [string substringWithRange:NSMakeRange(i,1)];
            NSLog(@"第%d个字是:%@",i,temp);
            if (self.delegate && [self.delegate respondsToSelector:@selector(predicateWithConetent:)]) {
                BOOL predicate = [self.delegate predicateWithConetent:temp];
                if (predicate) {
                    afterCutString = [afterCutString stringByAppendingString:temp];
                }
            } else{
                afterCutString =[afterCutString stringByAppendingString:temp];
            }
        }
        textField.text = afterCutString;
        return NO;
    } else {
        if (self.delegate && [self.delegate respondsToSelector:@selector(predicateWithConetent:)]) {
            BOOL predicate = [self.delegate predicateWithConetent:string];
            if (!predicate) {
                return NO;
            } else{
                return YES;
            }
        } else{
            return YES;
        }
    }
}


// 外层通过代理来判断是否满足条件
- (BOOL)predicateWithConetent:(NSString *)content {
    NSString * obj = nil;
    BOOL predicateStatus = YES;
    for(int i =0; i < [content length]; i++) {
        obj = [content substringWithRange:NSMakeRange(i,1)];
        if (![JNRegexPatternModel number_English_disorderPredicateWithContent:content]) {
            predicateStatus = NO;
        }
    }
    return predicateStatus;
}

```









------

[<返回目录](https://weadar.github.io/index)