---
order: 1
title:
  zh-CN: 水平方向的步骤条
  en-US: 'Horizontal Steps'
---

````jsx
/* eslint global-require: 0 */
import { Steps, WingBlank, WhiteSpace } from 'antd-mobile';

const Step = Steps.Step;

const steps = [{
  title: 'Finished',
  description: 'This is description',
}, {
  title: 'In Progress',
  description: 'This is description',
}, {
  title: 'Waiting',
  description: 'This is description',
}].map((s, i) => <Step key={i} title={s.title} description={s.description} />);

const customIcon = <img src="https://gw.alipayobjects.com/zos/rmsportal/hsDpIpVTdVdhfvcLseyy.svg" className="am-icon am-icon-md" alt="icon" />;

ReactDOM.render(
  <WingBlank mode={20} className="stepsExample">
    <div className="sub-title">Horizontal small size</div>
    <WhiteSpace />
    <Steps current={1} direction="horizontal" size="small">{steps}</Steps>
    <div className="sub-title">Horizontal default size</div>
    <WhiteSpace />
    <Steps current={1} direction="horizontal">{steps}</Steps>
    <div className="sub-title">Horizontal customized icon</div>
    <WhiteSpace />
    <Steps direction="horizontal">
      <Step title="Step 1" icon={customIcon} />
      <Step status="error" title="Step 2" icon={customIcon} />
      <Step title="Step 3" icon={customIcon} />
    </Steps>
    <div className="sub-title">Horizontal timeline mode</div>
    <WhiteSpace />
    <Steps current={-1} direction="horizontal" size="small" className="timeline">
      <Step title="Now" description="Buy" icon={<span className="fake-icon" />} />
      <Step title="Nov. 3rd" description="Buy success" icon={<span className="fake-icon" />} />
      <Step title="Nov. 4th" description="Profit arrival" icon={<span className="fake-icon" />} />
    </Steps>
  </WingBlank>
  , mountNode);
````

````css
.stepsExample .timeline.am-steps.am-steps-small
.am-steps-item.am-steps-custom
.am-steps-head-inner > .am-steps-icon {
  width: 8px;
  height: 8px;
  border-radius: 50%;
  background-color: #d9dff1;
}
.stepsExample .timeline.am-steps.am-steps-small .am-steps-tail {
  top: 3px;
  padding: 0 8px;
  background-color: transparent;
}
.sub-title {
  color: #888;
  font-size: 14px;
  padding: 30px 0 18px 0;
}
````
