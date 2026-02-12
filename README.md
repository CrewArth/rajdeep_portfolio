# rajdeep_portfolio

// Generic find - can find by any field
export const find = async (data) => {
  const { model, filter } = data;
  const result = await model.find(filter);
  return result;
};

// Generic findOne - can find one by any field
export const findOne = async (data) => {
  const { model, filter } = data;
  const result = await model.findOne(filter);
  return result;
};

// Create new document
export const create = async (data) => {
  const { model, data: createData } = data;
  const result = await model.create(createData);
  return result;
};

// Update one document
export const updateOne = async (data) => {
  const { model, filter, update } = data;
  const result = await model.findOneAndUpdate(filter, { $set: update }, { new: true });
  return result;
};

// Update many documents
export const updateMany = async (data) => {
  const { model, filter, update } = data;
  const result = await model.updateMany(filter, { $set: update });
  return result;
};

// Delete one document
export const deleteOne = async (data) => {
  const { model, filter } = data;
  const result = await model.findOneAndDelete(filter);
  return result;
};

// Delete many documents
export const deleteMany = async (data) => {
  const { model, filter } = data;
  const result = await model.deleteMany(filter);
  return result;
};
